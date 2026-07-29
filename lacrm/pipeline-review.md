---
title: Weekly pipeline review
connector: lacrm
tools: [lacrm_pipelines_list, lacrm_pipeline_list]
outcome: A stage-by-stage read on every open deal and what's gone quiet.
---

# Weekly pipeline review

Your CRM already knows which deals are stalling. It just won't tell you unless you go looking, stage by stage, one click at a time. This recipe asks for the whole picture at once, with the quiet ones called out.

Read-only. It reads your pipelines and reports back; it doesn't move deals, message anyone, or change a status.

## The prompt

```
Give me a review of my sales pipeline.

First list my pipelines so I know what's there, then for the main one
walk through it stage by stage. For each stage: how many items are in
it, and for each item the name, the current status, and when it was
last updated.

At the end, call out anything that hasn't been touched in over 30 days
as at-risk, sorted by how long it's been sitting.

Read only — don't change any statuses or contact anyone.
```

## Setup notes

- If you run more than one pipeline, name the one you want (`walk through my New Client pipeline`) — otherwise the assistant will ask, or start with the first it finds.
- Statuses are defined per pipeline in Less Annoying CRM, so the stage names in the output are yours, not generic ones.
- 30 days is a starting point, not a rule. A long enterprise cycle might want 60; transactional work might want 10.

## Variations

**One rep.** In a shared account:

> `Same review, but only deals assigned to [NAME].`

**Just the at-risk list.** When you only want the action items:

> `Skip the full walkthrough. Just show me deals with no activity in 30+ days, oldest first.`

**Movement since last week.** Reads as a genuine standup input:

> `What changed in the pipeline in the last 7 days — anything that moved stage, and anything new?`

**Follow through.** Once you've found the stalled ones, [Look up a contact and log a note](contact-lookup-and-log-note.md) records the call you make about them.
