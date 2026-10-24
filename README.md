<p align="center">
  <a href="https://trygotham.io"><img src="./assets/logo.png" width="88" height="88" alt="Gotham Legal AI logo"></a>
</p>

# Gotham Legal AI for Claude

**Indian legal research and your Gotham work, inside Claude. Nothing changes until you approve it in Gotham.**

[Website](https://trygotham.io) · [Setup guide](https://trygotham.io/docs/claude) · [Support](mailto:support@trygotham.io) · [Privacy](https://trygotham.io/privacy)

> **Preview.** Gotham for Claude is in private preview. You need a Gotham account, and your workspace owner or admin must turn Claude on for the workspace.

## What you can do

| Ask Claude to… | What happens |
| --- | --- |
| Research Indian law | Searches Indian case law and statutes and links each point to its source in Gotham. |
| Find your work | Finds your workspaces, documents, matters, workflows, playbooks and tabular reviews by name. |
| Organise a matter | Prepares a saved search, a new matter or a new matter name. |
| Run a workflow | Prepares a run of a published workflow with your documents. Runs use workspace credits. |
| Set up contract review | Prepares a draft playbook or a tabular review. Creating a review does not start the analysis. |
| Check on a change | Tells you whether an approved change has finished and opens the result. |

## Try it

- “Find Indian authorities on limitation for a contract claim, with links to the sources.”
- “In my Litigation workspace, find the Acme supply dispute and show its status.”
- “Prepare a run of the redline comparison workflow on the original and revised NDA in my Review workspace.”
- “Prepare a tabular review of those two NDAs with a confidentiality period column.”
- “Did that change finish? Open the result.”

Use the names you see in Gotham. If two items share a name, Claude asks which one you mean.

## Get started

**Before you start:** a workspace owner or admin turns Claude on in Gotham under **Settings › Integrations › Claude**. It is off by default.

**Claude (web and desktop)**
1. Open **Settings › Connectors** and choose **Add custom connector**.
2. Enter `https://cm.trygotham.io/mcp`.
3. Sign in with your Gotham account and choose **Allow**.

**Claude Code**
1. Add the Gotham server:
   `claude mcp add --transport http gotham https://cm.trygotham.io/mcp`
2. In Claude Code, run `/mcp`, choose the Gotham server and sign in with your Gotham account.

Already signed in to Gotham in your browser? You will not be asked for your password again.

To see or remove the connection later, open [Connected apps](https://app.trygotham.io/connect/claude/manage) in Gotham.

## You stay in control

1. **Claude prepares.** Claude asks Gotham to save the change and gives you a link.
2. **You approve in Gotham.** Open the link, check the details and choose **Approve** or **Don’t approve**. Nothing changes until you approve.
3. **Claude checks.** Ask Claude whether it finished. Requests expire if you do not decide in time; ask Claude to prepare them again.

Claude can only see what you can already see in Gotham, and only in workspaces where Claude is turned on.

## Privacy and limits

- Claude sends Gotham only what the task needs, such as a search query or the change you asked for. Gotham sends back source links, approval links and status.
- Gotham keeps a record of approval requests and connection activity for up to 13 months. Requests you never decide are removed seven days after they expire.
- This plugin contains one skill, a server address and a logo. It runs nothing on your computer and holds no passwords or keys.
- Never paste passwords or keys into a chat.
- Legal results need review by a qualified professional. Check dates, coverage and the original text. A search result alone does not show that a case is still good law.

See the [setup guide](https://trygotham.io/docs/claude) and [privacy policy](https://trygotham.io/privacy) for details.

## For developers

This package has one skill, `use-gotham`, and one remote server:

```json
{
  "mcpServers": {
    "gotham-claude": {
      "type": "http",
      "url": "https://cm.trygotham.io/mcp"
    }
  }
}
```

Validate it with `claude plugin validate . --strict`.

## About Gotham

[Gotham](https://trygotham.io) is a connected workspace for legal research and legal work, built India first, by Gotham Inc. This repository holds the Claude plugin only. It does not contain the hosted service or any customer data.

[Website](https://trygotham.io) · [Support](https://trygotham.io/contact) · [Privacy](https://trygotham.io/privacy) · [Terms](https://trygotham.io/terms) · [License](./LICENSE)

Copyright © 2026 Gotham Inc. All rights reserved. Public distribution requires Gotham's authorization under the [package license](./LICENSE).
