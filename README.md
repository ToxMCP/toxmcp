[![Release](https://img.shields.io/github/v/release/ToxMCP/toxmcp?sort=semver)](https://github.com/ToxMCP/toxmcp/releases)
[![DOI](https://img.shields.io/badge/DOI-10.64898%2F2026.02.06.703989-blue)](https://doi.org/10.64898/2026.02.06.703989)
[![License](https://img.shields.io/badge/License-Apache--2.0-blue.svg)](./LICENSE)
[![MCP](https://img.shields.io/badge/MCP-JSON--RPC-informational)](https://modelcontextprotocol.io/)

# ToxMCP Suite

**ToxMCP** is a suite of **guardrailed, auditable agentic workflows** for computational toxicology delivered through the **Model Context Protocol (MCP)**.

- Preprint (bioRxiv): https://doi.org/10.64898/2026.02.06.703989
- Citation metadata: [`CITATION.cff`](./CITATION.cff)

## Architecture

![ToxMCP architecture](./assets/toxmcp-architecture.jpg)

## Getting started

1) Pick a module below (CompTox is the recommended first run today).
2) Follow that repo’s **Quickstart TL;DR**.
3) Verify with the **Verification (smoke test)** curl snippet.

### Default ports (examples)

- CompTox MCP: http://localhost:8000
- O-QT MCP: http://localhost:8001
- PBPK MCP: http://localhost:8002
- AOP MCP: http://localhost:8003
- ADMETlab MCP: http://localhost:8200

## What is MCP?

MCP (Model Context Protocol) is a standard way for LLM clients/orchestrators to call external tools over a structured interface.
See the official MCP docs/spec: https://modelcontextprotocol.io/

## Modules

| Module | What it covers | Upstream dependency | Requirements | Status | Repo |
| --- | --- | --- | --- | --- | --- |
| **CompTox MCP** | Identity, hazard, exposure, bioactivity, screening prioritization | EPA CompTox APIs + packaged metadata bundles | **API key required** (`CTX_API_KEY`) | Available now | [Repo](https://github.com/ToxMCP/comptox-mcp) |
| **ADMETlab MCP** | Molecule washing, SVG rendering, ADMET prediction, CSV retrieval | ADMETlab 3.0 API | No key by default; upstream instability/rate limits may cause intermittent failures | Available now | [Repo](https://github.com/ToxMCP/admetlab-mcp) |
| **AOP MCP** | Mechanistic pathways, scientific review, assay discovery, authoring workflows | AOP-Wiki / AOP-DB / CompTox federation | Internet access recommended; fixture fallback available for offline development | Available now | [Repo](https://github.com/ToxMCP/aop-mcp) |
| **O-QT MCP** | OECD QSAR workflows, grouping/read-across dossiers, PDF reports | OECD QSAR Toolbox WebAPI | Requires a running QSAR Toolbox WebAPI instance (typically Windows-hosted) | Available now | [Repo](https://github.com/ToxMCP/oqt-mcp) |
| **PBPK MCP** | PBPK simulation, qualification, verification, dossier export | Open Systems Pharmacology Suite + `rxode2` runtime | Local worker/runtime setup required (see repo deploy scripts) | Available now | [Repo](https://github.com/ToxMCP/pbpk-mcp) |
| **Direct-Use Exposure MCP** | Coming soon | Coming soon | Coming soon | Coming soon | [Repo](https://github.com/ToxMCP/direct-use-exposure-mcp) |
| **Dietary Exposure MCP** | Coming soon | Coming soon | Coming soon | Coming soon | [Repo](https://github.com/ToxMCP/dietary-exposure-mcp) |
| **Environmental Fate MCP** | Coming soon | Coming soon | Coming soon | Coming soon | [Repo](https://github.com/ToxMCP/environmental-fate-mcp) |
| **Bioactivity-PoD MCP** | Coming soon | Coming soon | Coming soon | Coming soon | [Repo](https://github.com/ToxMCP/bioactivity-pod-mcp) |

### Which one should I try first?

- Start with **CompTox MCP** if you want the best first-run experience and the most
  recognizable toxicology dataset integration today.
- Then add **AOP MCP**, **O-QT MCP**, or **PBPK MCP** depending on whether you want
  mechanistic context, QSAR Toolbox automation, or PK workflows next.

Exposure-side stack expansion is in progress. The new module repos are linked above early so
you can follow them, while setup details for the `Coming soon` entries will land in those
repos directly as each module is published.

## Docs

Start here: [docs/README.md](./docs/README.md)

## Notes

- Each MCP server is versioned and released independently.
- Some modules depend on proprietary or rate-limited upstream services—check each module README for exact setup.

## Acknowledgements / Origins

ToxMCP was developed in the context of the **VHP4Safety** project (see: https://github.com/VHP4Safety) and related research/engineering efforts.

Funding: Dutch Research Council (NWO) — NWA.1292.19.272 (NWA programme)

This suite integrates with third-party data sources and services (e.g., EPA CompTox, ADMETlab, AOP resources, OECD QSAR Toolbox, Open Systems Pharmacology). Those upstream resources are owned and governed by their respective providers; users are responsible for meeting any access, API key, rate limit, and license/EULA requirements described in each module.

## License

Apache-2.0

## ✅ Citation

Djidrovski, I. **ToxMCP: Guardrailed, Auditable Agentic Workflows for Computational Toxicology via the Model Context Protocol.** bioRxiv (2026). https://doi.org/10.64898/2026.02.06.703989

```bibtex
@article{djidrovski2026toxmcp,
  title   = {ToxMCP: Guardrailed, Auditable Agentic Workflows for Computational Toxicology via the Model Context Protocol},
  author  = {Djidrovski, Ivo},
  journal = {bioRxiv},
  year    = {2026},
  doi     = {10.64898/2026.02.06.703989},
  url     = {https://doi.org/10.64898/2026.02.06.703989}
}
```

Citation metadata: [`CITATION.cff`](./CITATION.cff)

## Contributing

Please see [CONTRIBUTING.md](./CONTRIBUTING.md). If you’re not sure which repository to use, open an issue here: https://github.com/ToxMCP/toxmcp/issues

## Support

See [SUPPORT.md](./SUPPORT.md).
