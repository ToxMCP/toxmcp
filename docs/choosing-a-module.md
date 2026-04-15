# Choosing a module

A quick guide for first-time users.

## If you want the best first run today

- **CompTox MCP** — the recommended first module for the current stack; requires an EPA
  CompTox API key (`CTX_API_KEY`).
  - https://github.com/ToxMCP/comptox-mcp

## If you want authoritative toxicology datasets

- **CompTox MCP** — stable entry point for identity, hazard, exposure, bioactivity, and
  screening-prioritization workflows.
  - https://github.com/ToxMCP/comptox-mcp

## If you want rapid ADMET utilities

- **ADMETlab MCP** — still useful for quick ADMET-style utility workflows, but no longer the
  default first-run recommendation in the suite overview because the upstream service can be
  intermittently unstable.
  - https://github.com/ToxMCP/admetlab-mcp

## If you want mechanistic context / pathways

- **AOP MCP** — federates AOP-Wiki / AOP-DB / CompTox and now extends beyond discovery into
  scientific review and draft authoring workflows.
  - https://github.com/ToxMCP/aop-mcp

## If you want OECD QSAR Toolbox automation

- **O-QT MCP** — requires access to a running OECD QSAR Toolbox WebAPI instance and is aimed at
  workflow automation, grouping/read-across dossiers, and report generation.
  - https://github.com/ToxMCP/oqt-mcp

## If you want PBPK simulation workflows

- **PBPK MCP** — requires local runtime setup and covers execution, qualification,
  verification, and dossier export.
  - https://github.com/ToxMCP/pbpk-mcp

## Coming soon in the stack

- **Direct-Use Exposure MCP** — coming soon.
  - https://github.com/ToxMCP/direct-use-exposure-mcp
- **Dietary Exposure MCP** — coming soon.
  - https://github.com/ToxMCP/dietary-exposure-mcp
- **Environmental Fate MCP** — coming soon.
  - https://github.com/ToxMCP/environmental-fate-mcp
- **Bioactivity-PoD MCP** — coming soon.
  - https://github.com/ToxMCP/bioactivity-pod-mcp
