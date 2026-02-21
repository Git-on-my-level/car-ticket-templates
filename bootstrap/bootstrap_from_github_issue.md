---
agent: <strong planning model>
done: false
title: "Bootstrap from GitHub Issue"
goal: "Generate subsequent tickets based on GitHub issue"
---

# Input
Github Issue: [link_or_id]

# Your Task
- Read the github issue
- Understand what it's trying to accomplish
- Understand enough of the codebase to be able to write tickets which are actionable and have well defined end goals
- Generate a series of tickets, which when done in order, will accomplish the goal of the original issue
- The last ticket should be a final review ticket that double checks the work of the previous tickets and opens a pull request which closes the issue
