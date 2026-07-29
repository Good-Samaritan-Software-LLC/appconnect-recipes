# AppConnect Recipes

**[AppConnect](https://appconnect.goodsamsoftware.com)** connects the business tools you already use — FreshBooks and Less Annoying CRM — to the AI assistant you already talk to. You authorize the connection once, then ask for what you need in plain language instead of clicking through screens.

### 👉 [Get connected at appconnect.goodsamsoftware.com](https://appconnect.goodsamsoftware.com)

This repo is a curated, human-reviewed collection of **prompt recipes**: tested prompts that do something genuinely useful with a connected account. Copy one, paste it into your assistant, adjust the bits in `[brackets]`.

📖 Every recipe here also renders on the [AppConnect docs site](https://appconnect.goodsamsoftware.com/docs).

---

## Recipes

| Recipe | Connector | Outcome |
|---|---|---|
| [Overdue invoices summary](freshbooks/overdue-invoices-summary.md) | FreshBooks | A prioritized list of who owes you money and how late they are |
| [Draft an invoice from a description](freshbooks/draft-invoice-from-description.md) | FreshBooks | A draft invoice, ready for you to review and send |
| [Weekly pipeline review](lacrm/pipeline-review.md) | Less Annoying CRM | A stage-by-stage read on every open deal and what's gone quiet |
| [Look up a contact and log a note](lacrm/contact-lookup-and-log-note.md) | Less Annoying CRM | A call or meeting written to the right contact's history |

---

## Example recipe

Here's one in full, so you can see the shape before you browse:

### Overdue invoices summary

**Outcome:** a prioritized list of who owes you money and how late they are.

```
Show me every overdue invoice, oldest first.

For each one give me: the client's name, the invoice number, the amount
outstanding, the due date, and how many days past due it is.

Group them into three buckets — 1-30 days, 31-60 days, and 60+ days —
and give me a total dollar amount for each bucket.

Don't send anything to anyone. This is for my review only.
```

**Setup notes:** works as soon as your FreshBooks account is connected — no configuration needed. The last line is deliberate: it keeps the assistant reporting rather than acting.

---

## Repo layout

```
freshbooks/
  <recipe-slug>.md
lacrm/
  <recipe-slug>.md
```

Every recipe is a single markdown file with frontmatter:

```yaml
---
title: Overdue invoices summary
connector: freshbooks          # freshbooks | lacrm
tools: [invoice_list, client_list]
outcome: A prioritized list of who owes you money and how late they are.
---
```

`tools` must list the **actual** MCP tool names the recipe relies on. FreshBooks tools are bare (`invoice_list`), Less Annoying CRM tools carry the `lacrm_` prefix (`lacrm_contact_get`). Your assistant may display them under a namespace of its own — that's fine, use the canonical name here.

---

## Contributing

Recipes are welcome. Open a PR that adds one markdown file to the folder for its connector.

**Curation policy — please read before opening a PR:**

- **Every PR is reviewed by a human before it is merged.** Nothing lands automatically.
- A recipe must do what its `outcome` line says, and nothing else.
- **Recipes are rejected if they instruct the AI to send data anywhere, contact third parties, or take any action beyond the task described.** That includes emailing, posting to webhooks or external APIs, messaging contacts, or exfiltrating account data in any form.
- Prefer read-only recipes. If a recipe writes to an account, say so plainly in the intro and keep the write to a single, obvious, reviewable step.
- Every tool name in `tools` must be real. Invented or guessed tool names are an automatic rejection.
- Keep it concrete. A recipe should be something you have actually run against a real account.

Recipes are prompts, and prompts are instructions someone will run against their own live business data. We curate accordingly.

## License

[MIT](LICENSE)
