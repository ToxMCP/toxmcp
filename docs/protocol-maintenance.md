# MCP compatibility and maintenance plan

Reviewed against the public repositories and upstream documentation on 1 October
2026. Each module retains its existing supported transport during the current
security maintenance work. Dependency updates alone do not establish support
for a new protocol revision.

## Compatibility work to schedule

The [2026-07-28 MCP changelog](https://modelcontextprotocol.io/specification/2026-07-28/changelog)
changes negotiation and discovery: clients supply version metadata per request,
and servers implement `server/discover` instead of relying on an initialization
handshake. It also changes subscriptions, removes HTTP protocol sessions, and
requires explicit result types. A major SDK update therefore needs transport
and client interoperability checks.

The [Python SDK v2 release](https://github.com/modelcontextprotocol/python-sdk/releases/tag/v2.0.0)
is a candidate for Python modules. Existing v1 constraints are retained until
the checks below pass; they are deliberate compatibility boundaries.

| Modules | Migration focus |
| --- | --- |
| Direct-Use, Dietary, Environmental Fate | Test the Python SDK upgrade with installed-wheel stdio and HTTP clients, existing resource URIs, and scientific contracts. |
| Epigenomics | Review the TypeScript SDK's supported protocol revisions and transport APIs before changing its v1 dependency. Preserve authentication, origin validation, bounded requests, and Python qualification tools. |
| AOP, CompTox, O-QT, PBPK | Inventory each bridge's discovery, error, HTTP/stdio, authentication, and job behavior before selecting an adapter or SDK migration. |

Start with a separate Direct-Use prototype because its offline contracts and
installed-wheel tests provide a bounded baseline. Expand to the other SDK-based
modules after that baseline passes. Plan each custom bridge independently.

## Required compatibility evidence

For each candidate, record the exact server commit, SDK version, client version,
transport, and requested protocol revision. Run supported legacy clients and a
client implementing the new revision against the same installed distribution.
Cover discovery, tool listing/calling, resources, errors, version rejection,
authentication failures, origin/host rejection, request limits, cancellation,
and clean stdio shutdown. Exercise subscriptions only where the module offers
them. Check server-minted job handles and authorization across stateless HTTP
requests wherever jobs are implemented.

Retain schema, golden-payload, deterministic numerical, governance, and
scientific-boundary checks. Compare user-visible outputs with the prior release.
A successful handshake is insufficient evidence for a scientific module.

Publish a supported-client matrix only after these checks pass. Keep the prior
release available for rollback. Document any removed client support and use an
appropriate version increment before release.

## Routine maintenance

Run dependency and source-security checks on pull requests and at least weekly.
Keep patched dependency minimums in distribution metadata as well as locks.
Investigate failures before changing suppressions; record the advisory, reachable
code path, evidence, owner, and next review date for any exception.

Check scheduled workflows for inactivity disablement. GitHub documents that a
write-authorized commit changing the cron schedule can reactivate an inactive
workflow; verify its active state and a successful run after merging. See
[GitHub's schedule documentation](https://docs.github.com/en/actions/reference/workflows-and-actions/events-that-trigger-workflows#schedule).

Prepare patch releases when main contains security fixes missing from the latest
published package. Require current CI, a clean installed-artifact smoke, and any
module-specific upstream or scientific release gates before tagging. Review
older dependency pull requests against current main; close or supersede them
only after the replacement is merged and verified.
