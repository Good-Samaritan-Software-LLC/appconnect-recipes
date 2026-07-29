---
title: Look up a contact and log a note
connector: lacrm
tools: [lacrm_contact_list, lacrm_contact_get, lacrm_note_create]
outcome: A call or meeting written to the right contact's history, in your words.
---

# Look up a contact and log a note

The note you don't write in the ninety seconds after a call is the note that never gets written. This one takes dictation: find the person, confirm it's the right person, write it down.

**This recipe writes to your CRM.** It adds one note to one contact. It does not email anyone, change contact details, or move anything in a pipeline.

## The prompt

```
Find [CONTACT NAME] in my CRM.

Show me the matching record first — name, company, and email — so I can
confirm it's the right person before anything gets written.

Once I confirm, log this note against them:

"[WHAT WAS DISCUSSED. What they asked for, what you committed to, and
the date of anything you agreed.]"

Only add the note. Don't change any other field on the contact, and
don't contact them.
```

## Setup notes

- The confirm-first step is the important one. Common names and separate person/company records both make silent mismatches easy, and a note filed against the wrong contact is worse than no note — you'll trust it later.
- In Less Annoying CRM, people and companies are the same record type distinguished by a flag. If you get a company back when you wanted a person (or vice versa), say `I meant the individual person, not the company` and it'll narrow.
- Notes land in the contact's history with today's date.

## Variations

**Backdating.** For a call you're writing up late:

> `Log it against the contact but date it [DATE] — that's when the call actually happened.`

**Note plus follow-up.** Capture the commitment as well as the conversation:

> `Also create a task to follow up with them on [DATE] about [TOPIC].`

*(Adds `lacrm_task_create` to the tools this recipe uses — a second write, so review it the same way.)*

**Straight from a transcript.** If you have raw notes:

> `Here are my raw notes from the call: [PASTE]. Clean them into a short professional summary, show me the summary, and log it against [CONTACT NAME] once I approve.`
