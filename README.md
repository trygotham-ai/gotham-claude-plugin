<p align="center">
  <a href="https://trygotham.io"><img src="./assets/logo.png" width="88" height="88" alt="Gotham Legal AI logo"></a>
</p>

# Gotham Legal AI for Claude

**Indian legal research. Connected legal work. Your approval.**

Gotham Legal AI is a Claude plugin and remote Model Context Protocol (MCP)
integration being prepared by **Gotham Inc**. It is designed to bring Indian
case law, statutes and your authorized Gotham workspace into a single
conversation: find the source, find the matter and prepare the next step.

[Explore Gotham](https://trygotham.io) · [Contact the team](mailto:support@trygotham.io) · [Privacy](https://trygotham.io/privacy)

> **Private preview.** Not published or ready to connect. The dedicated
> service at `https://cm.trygotham.io/mcp` is not deployed by this
> preparation. Claude sign-in, permissions and live tool tests remain
> pending. Package validation is separate from directory approval.

## Legal research and workspace capabilities

The planned integration connects research to the work around it.

| Your task | Designed capabilities |
| --- | --- |
| Research Indian law | Search supported Indian case law and statutes, with links to the underlying sources in Gotham. |
| Find the right record | Discover accessible workspaces, documents, matters, workflows, playbooks and tabular reviews by name. |
| Organize a matter | Prepare a saved search, a new matter or a matter rename for approval. |
| Run a legal workflow | Prepare a published workflow with its declared inputs. Runs use workspace credits. |
| Set up contract review | Prepare an empty draft playbook or a tabular review. Creating a review does not start analysis. |
| Verify a change | Check the stored request's authoritative status and read the resulting record. |

For lawyers, law firms and in-house legal teams working with Indian legal
sources and existing Gotham records. This plugin exposes a focused set of
capabilities, rather than every feature of the wider Gotham platform.

## Example prompts

Use workspace and record names you recognize. The integration resolves
internal IDs through authorized discovery and clarifies duplicate names.

- **Legal research:** “Find Indian authorities on limitation for a contract claim, with links to the original sources.”
- **Matter management:** “In my Litigation workspace, find the Acme supply dispute and show its status.”
- **Workflow preparation:** “Find the published comparison workflow and prepare a run using the original and revised NDA in my Review workspace.”
- **Contract review:** “Prepare a tabular review of those two NDAs with a confidentiality-period column.”
- **After approval:** “Check whether that approved request finished and open the resulting record.”

These examples are not test-pass receipts. Names must match resources the
connected user can access.

## You approve changes in Gotham

1. **Prepare.** Claude asks Gotham to store the requested change and returns
   its summary, consequences, expiry and approval link.
2. **Review and approve.** Check the exact request on its Gotham page. It
   executes only after approval there. OAuth consent and a chat reply do
   not replace approval of a stored request.
3. **Check the result.** Ask Claude to check that request's status. A
   workflow may continue after approval; a prepared request is not a
   completed run. Expired requests need a new preparation.

Automatic continuation and background monitoring in Claude are not
promised by this preview.

## Connect after release

You will need a Gotham account, access to the intended workspace, relevant
product entitlements and the separately released Claude connection
enabled by a workspace administrator.

Once the service is released and setup is verified:

1. Install Gotham Legal AI in a supported Claude app.
2. Connect Gotham through the plugin's Connectors tab and sign in using
   OAuth. In Claude Code, use `/mcp` to authenticate the remote server.
3. Name the workspace you want. A workspace open in your browser does not
   establish the connector's workspace.
4. Grant `gotham:read` for reads. Preparing a change additionally requires
   `gotham:write`; the service must enforce the granted scopes.

Never paste passwords, tokens or API keys into a conversation or this
repository. This private preview has no public marketplace install command.
The Claude connection is released independently; do not substitute another
provider's endpoint.

## Privacy, access and legal-source limits

The planned service must follow the connected user's Gotham permissions,
workspace rules, product entitlements and credit checks. Claude sends
selected tool arguments over HTTPS: a research query, chosen
workspace/resource handles or the requested change. Gotham returns bounded
metadata, source links, approval links and operation status.

The package contains a skill, JSON configuration and a logo. It has no
shell commands, local MCP process, hooks, installers, background agents or
embedded credentials. It does not ask Claude to export unrelated files,
memory or conversation history. Service data handling and retention still
need verification against the isolated deployment before any directory
attestation.

Legal output requires qualified professional review. Confirm source
coverage, dates and original text. Search alone does not establish that a
case is good law, an interpretation is correct or a term is enforceable.

## For developers and reviewers

One skill, `use-gotham`, and one remote MCP configuration:

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

Validate with the official Claude Code CLI:

```sh
claude plugin validate . --strict
```

Then validate the exact source commit in the directory portal. Source
checks do not verify OAuth or live behavior. Every advertised tool still
needs acceptance testing in Claude and MCP Inspector before the testing
confirmation can be selected. Source and documentation remain private
until an authorized public release.

## About Gotham Inc

[Gotham](https://trygotham.io) builds a connected workspace for legal
research and legal operations, with an India-first focus. This repository
contains the Claude plugin package, not the hosted service or customer data.

**Developer:** Gotham Inc · **Contact:** [support@trygotham.io](mailto:support@trygotham.io)

[Website](https://trygotham.io) · [Support](https://trygotham.io/contact) · [Privacy policy](https://trygotham.io/privacy) · [Terms](https://trygotham.io/terms) · [License](./LICENSE)

Copyright © 2026 Gotham Inc. All rights reserved. Public distribution
requires Gotham's authorization under the [package license](./LICENSE).
