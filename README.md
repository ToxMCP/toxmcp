[![Release](https://img.shields.io/github/v/release/ToxMCP/toxmcp?sort=semver)](https://github.com/ToxMCP/toxmcp/releases)
[![GitHub stars](https://img.shields.io/github/stars/ToxMCP/toxmcp?style=social)](https://github.com/ToxMCP/toxmcp/stargazers)
[![DOI](https://img.shields.io/badge/DOI-10.64898%2F2026.02.06.703989-blue)](https://doi.org/10.64898/2026.02.06.703989)
[![License](https://img.shields.io/badge/License-Apache--2.0-blue.svg)](./LICENSE)
[![MCP](https://img.shields.io/badge/MCP-JSON--RPC-informational)](https://modelcontextprotocol.io/)

# ToxMCP Suite

**ToxMCP** is the **public suite hub** for **guardrailed, auditable MCP servers** across computational toxicology, exposure science, mechanistic reasoning, QSAR workflows, ADMET utilities, and downstream kinetic modeling.

If you want the single best place to follow the public suite, module launches, and onboarding path, **star this repo**.

- Preprint (bioRxiv): https://doi.org/10.64898/2026.02.06.703989
- Citation metadata: [`CITATION.cff`](./CITATION.cff)

## Why Star This Repo?

- It is the **canonical public index** for the ToxMCP suite.
- It is the best place to track **which modules are public now** versus still in progress.
- It is the suite-level home for **docs, architecture, quickstart guidance, and contribution links**.

## Architecture

![ToxMCP architecture](./assets/toxmcp-architecture-2026.jpg)

## What Is MCP?

MCP (Model Context Protocol) is a standard way for LLM clients and orchestrators to call external tools over a structured interface.
See the official MCP docs/spec: https://modelcontextprotocol.io/

## Public Suite Today

| Module | What it covers | Upstream dependency | Requirements | Status | Repo |
| --- | --- | --- | --- | --- | --- |
| **CompTox MCP** | Identity, hazard, exposure, bioactivity, screening prioritization | EPA CompTox APIs + packaged metadata bundles | **API key required** (`CTX_API_KEY`) | Available now | [Repo](https://github.com/ToxMCP/comptox-mcp) |
| **ADMETlab MCP** | Molecule washing, SVG rendering, ADMET prediction, CSV retrieval | ADMETlab 3.0 API | No key by default; upstream instability/rate limits may cause intermittent failures | Available now | [Repo](https://github.com/ToxMCP/admetlab-mcp) |
| **AOP MCP** | Mechanistic pathways, scientific review, assay discovery, authoring workflows | AOP-Wiki / AOP-DB / CompTox federation | Internet access recommended; fixture fallback available for offline development | Available now | [Repo](https://github.com/ToxMCP/aop-mcp) |
| **O-QT MCP** | OECD QSAR workflows, grouping/read-across dossiers, PDF reports | OECD QSAR Toolbox WebAPI | Requires a running QSAR Toolbox WebAPI instance (typically Windows-hosted) | Available now | [Repo](https://github.com/ToxMCP/oqt-mcp) |
| **PBPK MCP** | PBPK simulation, qualification, verification, dossier export | Open Systems Pharmacology Suite + `rxode2` runtime | Local worker/runtime setup required (see repo deploy scripts) | Available now | [Repo](https://github.com/ToxMCP/pbpk-mcp) |
| **Direct-Use Exposure MCP** | Auditable deterministic external-dose scenario construction, jurisdictional comparison, PBPK-ready handoff packaging | Versioned defaults, packaged archetypes, bounded worker/exchange surfaces | Python 3.12+; local install from repo release assets | Available now | [Repo](https://github.com/ToxMCP/direct-use-exposure-mcp) |
| **Dietary Exposure MCP** | Food-mediated oral exposure screening, governed residue and consumption review, and PBPK-ready oral dose handoffs | Versioned defaults plus governed residue, consumption, reference-value, legal, and source registries | Python 3.12+; install the verified wheel from GitHub release assets; local stdio operation | Available now (`v0.1.0`; **screening only**) | [Repo](https://github.com/ToxMCP/dietary-exposure-mcp) / [Release](https://github.com/ToxMCP/dietary-exposure-mcp/releases/tag/v0.1.0) |
| **Environmental Fate MCP** | Environmental release-to-concentration screening, scientific review, erosion/sediment transport screening, and downstream regulatory handoff packaging | Versioned defaults, packaged schemas/examples, release artifacts, and optional normalized external payloads | Python 3.12+; local install from repo release assets | Available now (`v0.5.0`) | [Repo](https://github.com/ToxMCP/environmental-fate-mcp) / [Release](https://github.com/ToxMCP/environmental-fate-mcp/releases/tag/v0.5.0) |
| **Epigenomics MCP** | Processed epigenomic feature qualification, scientific review, and Bioactivity-PoD handoff packaging | Processed feature, design, and provenance inputs; packaged GEO fixture; optional external integration clients | Node.js 20+; local stdio or loopback HTTP; no API key for core workflows | Available now (`v0.2.1`; **qualification and handoff only**) | [Repo](https://github.com/ToxMCP/epigenomics-mcp) / [Release](https://github.com/ToxMCP/epigenomics-mcp/releases/tag/v0.2.1) |
| **Bioactivity-PoD MCP** | Coming soon | Coming soon | Coming soon | Coming soon | [Repo](https://github.com/ToxMCP/bioactivity-pod-mcp) |

## Getting Started

The fastest way to get productive with ToxMCP is:

1. Pick an entry point.
   Start with **CompTox MCP** for the most recognizable public toxicology data workflow, **Direct-Use Exposure MCP** for product-use exposure scenarios, **Dietary Exposure MCP** for food-mediated oral screening, or **Epigenomics MCP** for processed epigenomic evidence qualification.
2. Follow that module repo’s **Quickstart TL;DR**.
3. Run its **Verification (smoke test)** so you know the local setup is working before adding more modules.

### Common Local Ports

- CompTox MCP: http://localhost:8000
- O-QT MCP: http://localhost:8001
- PBPK MCP: http://localhost:8002
- AOP MCP: http://localhost:8003
- ADMETlab MCP: http://localhost:8200

### Which one should I try first?

- Choose **CompTox MCP** if you want the best first-run experience and the most recognizable toxicology dataset integration today.
- Choose **Direct-Use Exposure MCP** if you need reviewable exposure scenarios with explicit assumptions, provenance, limitations, and fit-for-purpose framing.
- Choose **Dietary Exposure MCP** if you need screening-only food-mediated oral exposure calculations, governed residue and consumption review, or a PBPK-ready oral dose handoff.
- Choose **Environmental Fate MCP** if you need auditable environmental release-to-concentration screening, scalar erosion/sediment transport screening, scientific review packets, or downstream concentration handoff packages.
- Choose **Epigenomics MCP** if you need bounded qualification of processed methylation or region-level features, explicit scientific limitations, or a governed Bioactivity-PoD handoff.
- Add **AOP MCP**, **O-QT MCP**, or **PBPK MCP** next depending on whether the workflow needs mechanistic context, QSAR Toolbox automation, or toxicokinetic modeling.

The direct-use, dietary, and environmental-fate exposure layers are now public. `Direct-Use Exposure MCP` covers deterministic product-use external-dose screening; `Dietary Exposure MCP v0.1.0` covers food-mediated oral screening and governed evidence handoffs; and `Environmental Fate MCP` covers bounded environmental release-to-concentration screening. Each remains a bounded screening service rather than a final safety or regulatory decision engine.

`Epigenomics MCP v0.2.1` is also public as a qualification-and-handoff layer for already processed epigenomic evidence. It does not perform raw sequencing, methylation calling, causal inference, clinical interpretation, or final regulatory decision-making.

## Docs

Start with [docs/README.md](./docs/README.md) for the suite-level documentation map.

## Notes

- Each MCP server is versioned and released independently.
- Some modules depend on proprietary or rate-limited upstream services. Check each module README for exact setup details.

## Acknowledgements / Origins

ToxMCP was developed, in part, in the context of the **VHP4Safety** project (see: https://github.com/VHP4Safety) and related research and engineering efforts.

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
