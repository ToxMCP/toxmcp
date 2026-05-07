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

## If you want auditable exposure-scenario construction

- **Direct-Use Exposure MCP** — the public suite module for deterministic external-dose
  screening, jurisdictional comparison, and PBPK-ready handoff packaging with explicit
  assumptions, provenance, limitations, and fit-for-purpose guidance.
  - https://github.com/ToxMCP/direct-use-exposure-mcp

## If you want environmental fate / concentration screening

- **Environmental Fate MCP** — the public suite module for bounded environmental
  release-to-concentration screening, scalar erosion/sediment transport screening,
  scientific review packets, and downstream concentration handoff packages.
  - https://github.com/ToxMCP/environmental-fate-mcp
  - Current release: https://github.com/ToxMCP/environmental-fate-mcp/releases/tag/v0.2.0

## If you want processed imaging bioactivity qualification

- **Phenotypic Imaging Bioactivity MCP** — private/local-RC staging module for
  processed high-content imaging, Cell Painting, CellProfiler, pycytominer, and
  cell-health feature tables. Use it when you need auditable QC, cytotoxicity
  context, feature qualification, and Bioactivity-PoD handoff packets without
  raw-image processing or PoD fitting inside the imaging server.
  - Repository: private staging (`ToxMCP/phenotypic-imaging-bioactivity-mcp`)
  - Status: local release candidate; public release visibility still to be confirmed.

## Coming soon in the stack

- **Dietary Exposure MCP** — coming soon.
  - Repository: planned
- **Bioactivity-PoD MCP** — coming soon.
  - Repository: planned
