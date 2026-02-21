---
agent: <strong planning agent>
done: false
title: "Meta: multi-agent review (create review tickets)"
goal: "Generate independent review tickets and a synthesis ticket"
reasoning: medium
---

> Template note: This ticket’s job is to create the review tickets. It does not perform the review itself.

## Inputs (fill in)
- Target to review: [FILL_ME — commit sha / branch / milestone ticket path]
- Risk level: [low | medium | high]
- Reviewers to use:
  - Reviewer A agent: [opencode]
  - Reviewer B agent: [codex]
  - Synthesis agent: [codex]

## Context to load
- `.codex-autorunner/workspace/spec.md`
- The milestone ticket being reviewed: [FILL_ME]
- Any relevant repo docs: [FILL_ME]

## Create these tickets (required)
- [ ] Review A: independent review (no reading Review B output first)
- [ ] Review B: independent review (no reading Review A output first)
- [ ] Review Synthesis: reconcile A+B into a single actionable list

### Suggested structure
- Review A ticket uses: `reviews/review_single.md`
- Review B ticket uses: `reviews/review_single.md` (but different agent)
- Synthesis ticket uses: `reviews/review_synthesis.md`

If templates feature is enabled, you may apply templates:

```bash
car templates apply [TEMPLATE_REPO_ID]:reviews/review_single.md --into tickets --next
```

Then edit each created ticket:
- Set `title` to “Review A …”, “Review B …”
- Ensure each review ticket includes the same target and acceptance criteria

## Definition of done
- [ ] The 3 follow-up tickets exist and are clearly linked to the same target.
