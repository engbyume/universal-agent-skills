---
name: progressive-codex-model-router
description: >-
  Coordinate Codex work as a foreman. Route subagents to the lowest-cost capable
  model and effort, keep the parent on GPT-6 Luna / max, and aggregate child work.
  Designed to stretch Codex usage for ChatGPT Plus users, currently listed at
  $20/month.
---

# Progressive Codex Model Router

Use this skill when a Codex task can benefit from delegated work. Keep the main
agent, or parent, on GPT-6 Luna / max. The model picker controls delegated
subagents only. It does not change the parent.

The parent acts as the foreman. It splits work into clear tickets, chooses the
lowest-cost model and effort that meet each ticket's quality and risk needs,
assigns child agents, gathers their results, and integrates, verifies, and
accepts the work. The parent keeps ownership of shared files and final decisions.

ChatGPT Plus is currently listed at $20/month. Codex usage is included, subject
to plan, account, and task limits. This workflow helps Plus users stretch that
allowance by using efficient routes on routine work and stronger routes only
when needed. API token prices are separate from subscription usage. Check
current pricing and model access because they can change. See [ChatGPT Plus](https://help.openai.com/en/articles/6950777-what-is-chatgpt-plus)
and [Using Codex with your ChatGPT plan](https://help.openai.com/en/articles/11369540-using-codex-with-your-chatgpt-plan).

## Model-to-task breakdown

| Work | Child model and effort | Use |
|---|---|---|
| Parent or main agent | GPT-6 Luna / max | Keep the parent on this route. The child picker cannot change it. |
| Easy or routine implementation | GPT-6 Luna / max | Low-cost, capable route for bounded work. |
| Read-only research, audit, review, or verification | GPT-6 Luna / max | Use a fresh child for independent review. |
| Medium implementation | GPT-6.1 Terra / medium | Use for scoped implementation and visual or computer-use tasks. |
| Hard, complex, or high-risk implementation | GPT-6.1 Sol / medium | Use when the task needs stronger reasoning or integration. |
| Ultra-complex implementation estimated under 10 minutes | GPT-6.1 Sol / high | For 10 minutes or more, or unknown duration, use medium. |
| Astra | User request only | Do not select automatically. |

These are starting routes. Pick the least costly eligible lane that meets the
task's quality floor. Consider parent context, tools, retries, repair, review,
and integration when estimating total cost. Do not select the most capable
model for every ticket. Do not treat cheap tokens or parallel workers as the
goal; the goal is a correct accepted result.

## Delegate and aggregate

1. Keep simple work with the parent when delegation overhead exceeds the gain.
2. Split only independent or clearly bounded work.
3. Give each child the task, context, allowed tools, exact write scope, success
   check, stop rule, and return format.
4. Set `model` and `reasoning_effort` on each child spawn. Use
   `fork_turns: "none"` when the child needs a different route from the parent.
5. The parent collects child reports, integrates work, checks evidence, and
   decides whether to accept the result. Child completion is not final acceptance.
6. Use one writer for overlapping files. Use fresh context for an independent
   read-only review.
7. If the runtime cannot set or verify the child route, do the work in the parent
   instead of guessing.

## Authority and availability

This skill selects model routes. It does not grant permission to edit shared
files, send messages, spend money, publish, deploy, delete data, or access an
account. Follow the user's existing authorization and confirmation rules.

Model availability, picker controls, effort settings, and usage limits vary by
client and plan. If a model is unavailable, use another route only if it remains
authorized and meets the task requirements. Otherwise keep the work with the
parent and report the limit.
