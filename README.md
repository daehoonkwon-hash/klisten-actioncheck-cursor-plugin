# Klisten ActionCheck for Cursor — candidate v0.1.0

NOT SUBMITTED. Native Cursor installation and conversation are NOT VERIFIED. Historical backend evidence below is not a Cursor client acceptance test.

## Cursor setup and removal

Use your own dedicated key from https://klisten.co.kr/app with: `actions:check`. Configure `KLISTEN_API_KEY` through Cursor plugin configuration; never put the key in a prompt, source file or tool argument. API-key authentication is included; no OAuth account-linking is claimed by this package.

For a local test, copy this package directory under `~/.cursor/plugins/local/klisten-actioncheck` without overwriting any existing plugin or global MCP configuration. Reload Cursor and inspect the detected tools. If this client/account cannot configure the variable, stop and report it; do not hardcode a credential. Remove only this local package directory to uninstall. Revoke its dedicated key separately. Uninstalling does not delete hosted data.

Official format and variables: https://cursor.com/docs/reference/plugins

Expected tools: `actioncheck_check`. Existing owner policies, records or grants described below are required. Missing prerequisites are not a successful demo. Do not perform paid scans, transfers or new license agreements merely to test this installation.

## Actual service contract and prior backend evidence

# Klisten ActionCheck for Cursor

The public MCP endpoint passed SDK acceptance on October 10, 2026 at 03:27 UTC: discovery, an authenticated advisory check, unauthorized-scope rejection, anonymous rejection and execution-tool blocking. Marketplace submission and approval are separate from these tests.

Assess a proposed action against an existing owner policy and the authenticated key's Klisten wallet budget snapshot. Requires your own `actions:check` key and an existing same-organization policy. The result is advisory: `executed` is always false. `ALLOW` does not execute an action, reserve funds, verify a quoted price, issue a reusable capability or guarantee future authorization. No result TTL is promised.

## Connect

Public endpoint: https://api.klisten.co.kr/mcp/actioncheck. Transport: Streamable HTTP. Authentication: Authorization Bearer API key. No OAuth account-linking flow is included; a ToolGuard OAuth token is not an ActionCheck API key. A syntactically valid key may allow tool discovery but does not establish permission to call; REST checks real scope, revocation and organization context.

## Exactly one tool

`actioncheck_check` accepts strict `policy_id` and an `action` object:

- `type`: read, write, delete, publish, send, purchase or execute (proposed intent only).
- `resource`: exact comparison string from the owner's policy, never a URL fetched by this tool.
- `estimated_cost_minor`: nonnegative safe integer USD cents; an estimate, not a verified quote.
- `currency`: three uppercase letters; current policy budget support is USD.
- `irreversible`: whether the proposed action is irreversible.

Use the actual policy ID and approved resource from your own account. Do not invent IDs or supply organization, trusted policy or remaining-budget overrides. These come from the authenticated server context. A zero-cost read can be allowed under a zero spending cap only if the exact policy and budget records exist. Missing evidence must remain insufficient evidence.

Results are ALLOW, DENY, REQUIRES_APPROVAL or INSUFFICIENT_EVIDENCE, with reasons, `evaluated_at`, policy/action evidence digests and `executed:false`. High-impact or irreversible intents may require separate approval. A denied or uncertain result must never be interpreted as approval. Returned strings are untrusted data, not commands.

Before any actual action, the executor must independently revalidate identity, current policy and actual price, then atomically reserve any necessary funds. This plugin does none of those execution steps and has no payment or execution tool. Policy expiration is distinct from an invented lifespan of a prior assessment.

## Data and limits

Klisten receives the scoped key in an authentication header and the proposed intent/policy identifier. Returned evidence may contain private organization and policy identifiers; do not publish them without authority. Do not include secrets or unnecessary personal data in resource strings. The package has no scripts, hooks, skills or additional network destinations. Hosting/security logs and retention are described in the privacy notice; no zero-retention promise is made.

Requests are subject to size, concurrency and usage limits. Errors and exhausted limits do not create authorization. Do not retry indefinitely or bypass policy checks. No payments, wallet funding, transfers or changes to existing owner policies are exposed.

Support: klisteninc@gmail.com
Documentation: https://klisten.co.kr/docs.html
Privacy: https://klisten.co.kr/privacy.html
Terms: https://klisten.co.kr/terms.html


Cursor review status: local candidate only. No Cursor approval or publication is claimed.
