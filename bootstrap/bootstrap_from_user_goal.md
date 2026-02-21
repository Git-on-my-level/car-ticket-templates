---
agent: <strong planning model>
done: false
title: "Bootstrap from User Goal"
goal: "Generate subsequent tickets based on user goal"
---

# Goal
[USER_GOAL_HERE]]

# Your Task
- Understand the user's goal and the codebase
- You should apply your own taste and judgement and avoid asking the user questions, but if there are true blockers or extremely high leverage decisions which need user input, you should pause now and ask the user
- Once you have a clear understanding of how to accomplish the user's goal, generate a series of tickets, which when done in order, will accomplish the goal of the original issue
- The last ticket should be a final review ticket that double checks the work of the previous tickets and opens a pull request which closes the issue
