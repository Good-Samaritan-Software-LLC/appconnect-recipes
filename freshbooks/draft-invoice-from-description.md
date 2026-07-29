---
title: Draft an invoice from a description
connector: freshbooks
tools: [client_list, item_list, invoice_create]
outcome: A draft invoice, ready for you to review and send.
---

# Draft an invoice from a description

Describe the work in the way you'd describe it to a colleague, and get back a draft invoice with the line items filled in. The tedious part of invoicing isn't deciding what to charge — it's the clicking.

**This recipe writes to your account.** It creates one invoice, as a **draft**. Drafts are not sent to anyone and can be edited or deleted in FreshBooks. Nothing reaches the client until you send it yourself.

## The prompt

```
Create a draft invoice for [CLIENT NAME].

The work was:
- [DESCRIPTION], [QUANTITY] at [RATE]
- [DESCRIPTION], [QUANTITY] at [RATE]

Before you create it, check whether I already have saved items matching
these descriptions and reuse them if so, so my pricing stays consistent.

Create it as a DRAFT only. Do not send it, and do not email the client.
Show me what you created so I can review it.
```

## Setup notes

- Fill in the bracketed parts. A line can be anything you'd normally bill: `12 hours of consulting at $150/hour`, `1 site audit at $2,400`.
- The "check saved items" step matters more than it looks. Reusing your existing items keeps rates consistent with past invoices instead of re-deriving a price from whatever you typed today.
- Draft invoices carry no invoice number until sent, so a discarded draft leaves no gap in your numbering.
- If the client name is ambiguous, the assistant will ask which one you meant rather than guessing. That's intended — confirm before it writes.

## Reviewing before you send

The draft lands in FreshBooks under **Invoices → Drafts**. Check the line items, tax treatment, and due date, then send it from FreshBooks yourself.

To have the assistant read it back before you switch windows:

> `Show me the draft you just created, line by line, with the total.`

## Variations

**From tracked time.** If you've been logging hours against the client:

> `Draft an invoice for [CLIENT NAME] covering my unbilled time from [DATE] to [DATE]. Draft only — don't send it.`

**With terms.** Bill on something other than your default:

> `Same, but set payment terms to net 15 and add the note "Thanks — [PROJECT NAME] phase 1."`
