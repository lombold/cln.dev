+++
title = 'My OpenCode Workflow'
date = 2026-06-15T18:33:11+02:00
draft = true
version = 1
author = 'Colin'
categories = ['OpenCode', 'Workflow', 'TDD', 'Quality Gate', 'Conventional Commits']
+++

# Prerequisites:
your project must have a thoroughly executed set of lining rules, arch rules, and testing concept.

# make a list of system requirements & NFRs

# let the agent write structured tasks based on the requirements (Important: verification step)


# Execution Contract:
One-time kickoff prompt (copy/paste)
Execute TASK-23 through TASK-30 autonomously in order.
For each task:
1) implement via TDD,
2) run full frontend quality gate (test, lint, build),
3) stage all changes,
4) commit immediately using Conventional Commit style (feat|fix|chore: ...),
5) continue with next task without waiting for me.
   Do not stop between tasks unless truly blocked. If blocked, explain the blocker and your recommended default.
   At the end, provide a compact report with:
- tasks completed
- commit hashes + messages
- any deviations/assumptions
- final quality gate status.