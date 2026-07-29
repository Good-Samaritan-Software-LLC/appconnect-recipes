---
title: Overdue invoices summary
connector: freshbooks
tools: [invoice_list, client_list]
outcome: A prioritized list of who owes you money and how late they are.
---

# Overdue invoices summary

The report you actually want on a Monday morning: not "here are your invoices," but *who is late, by how much, and how badly*. Aging buckets are what turn a list into a collections decision — a client 70 days past due needs a phone call, one at 12 days needs nothing yet.

This recipe is read-only. It looks at your invoices and reports back; it does not contact anyone.

## The prompt

```
Show me every overdue invoice, oldest first.

For each one give me: the client's name, the invoice number, the amount
outstanding, the due date, and how many days past due it is.

Group them into three buckets — 1-30 days, 31-60 days, and 60+ days —
and give me a total dollar amount for each bucket.

Don't send anything to anyone. This is for my review only.
```

## Setup notes

- Works immediately once your FreshBooks account is connected — nothing to configure.
- The assistant pulls invoices filtered to overdue status and resolves client names against your client list, so the output reads with real names rather than numeric IDs.
- If you have a large invoice history, add a scope line to keep it fast and relevant:
  > `Only look at invoices from the last 12 months.`
- The final line is doing real work. Without it, an assistant may helpfully offer to draft chase emails. Keep it if you want a report and nothing more.

## Variations

**Single client.** When you're preparing for one specific conversation:

> `Same thing, but only for [CLIENT NAME].`

**Just the headline.** When you want the number and not the detail:

> `Just give me the total outstanding across all overdue invoices, and the single oldest one.`

**Weekly delta.** Useful as a standing Monday prompt:

> `Also flag which of these became overdue in the last 7 days.`
