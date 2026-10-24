# Gotham Legal AI for Claude

**Private preparation draft — not published and not ready to connect.**
The configured Claude-only host, `claude-mcp.trygotham.io`, is proposed and
has not been deployed by this preparation task. Do not replace it with
Gotham's ChatGPT endpoint. The Claude runtime and its authentication must be
released independently before this package can pass live acceptance.

Gotham brings legal research and workspace operations into Claude. The
intended connector searches supported Indian case law and statutes with
links to Gotham's source readers, and finds accessible matters, workflows,
playbooks and tabular reviews. It can prepare changes for the user to
review and approve in Gotham. Research output needs a qualified
professional's review; search snippets do not establish subsequent
treatment, enforceability or complete coverage.

## Intended setup after the separate service is released

1. Install the Gotham Legal AI plugin in a supported Claude app.
2. In the plugin's Connectors tab, add the Gotham connector and sign in to
   Gotham through OAuth. In Claude Code, use `/mcp` to authenticate the
   plugin's remote server. Never paste a password, bearer token or API key
   into a chat or this package.
3. Select a workspace by its name in your request. A workspace
   administrator must have enabled the separately released Claude
   connection. Signing in does not grant access to other workspaces.
4. Read tools require `gotham:read`. Preparing a change additionally
   requires `gotham:write`; the service must enforce the granted scopes.
5. For a change, review the returned summary and open the Gotham approval
   link. The request executes only after approval on that page. The
   connection's OAuth consent is separate from approval of each change.

Authentication and these setup steps have **not** yet been verified in
Claude. Directory listing and plugin publication are separate submissions.

## Example requests

- Find Indian authorities on limitation for a contract claim, with links.
- In my named Gotham workspace, open a matter and show its current status.
- Find a published workflow and the named documents it needs, and prepare
  its run for my approval.
- Show an existing playbook and prepare a new empty draft.
- Prepare a two-document tabular review with a confidentiality-period
  column. Creating a review does not start its analysis.

Names are resolved through authorized discovery; users should not have to
look up internal IDs. Workflow runs use workspace credits. Prepared
requests can expire and must not be represented as completed work.

## What this package runs and sends

This package contains Markdown instructions, a JSON manifest, one image
and a remote MCP configuration. It has no shell commands, local MCP
process, hooks, agents, package installers, background monitors, channels,
embedded credentials or automatic update scripts. Installing the package
does not start a workflow or create a Gotham record.

When a user asks for Gotham work, Claude sends the selected tool arguments
to the configured Gotham Claude service over HTTPS. Intended arguments
include the research query or the chosen workspace/resource handles and
requested change. Gotham returns authorized, bounded metadata, source
links, approval links and operation status. It does not ask Claude to
export its memory, conversation history, unrelated files or credentials.
Users should avoid including unrelated confidential material in queries.

The planned service uses the user's Gotham permissions and the product's
normal access and credit checks. Its data handling and retention must be
verified against the isolated deployed implementation before the directory
data-handling answers are attested. This draft does not promise a deployed
privacy implementation or automatic continuation in Claude. Check status
explicitly after approval; MCP Events support is not claimed.

## Privacy and support

Developer: **Gotham Inc**. Contact: **support@trygotham.io**.

- [Gotham privacy policy](https://trygotham.io/privacy)
- [Gotham terms](https://trygotham.io/terms)
- [Support](https://trygotham.io/contact)

The repository is private during preparation. Its README must become
publicly accessible, or a public setup guide must be published, before
listing launch. The current license reserves all rights pending Gotham's
public-distribution decision.

## Validation and release status

Run `claude plugin validate . --strict` with a current Claude Code version
from this folder, then validate the source commit in the developer portal.
Syntax validation does not prove OAuth, tool behavior or directory
approval. Every advertised tool must pass through the separate service in
Claude and MCP Inspector before the test confirmation can be selected.
