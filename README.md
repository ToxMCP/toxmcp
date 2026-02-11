# ToxMCP Suite

**ToxMCP** is a suite of **guardrailed, auditable agentic workflows** for computational toxicology delivered through the **Model Context Protocol (MCP)**.

- Preprint (bioRxiv): https://doi.org/10.64898/2026.02.06.703989
- Citation metadata: [`CITATION.cff`](./CITATION.cff)

## Architecture

![ToxMCP architecture](./assets/toxmcp-architecture.jpg)

## What is MCP?

MCP (Model Context Protocol) is a standard way for LLM clients/orchestrators to call external tools over a structured interface.
See the official MCP docs/spec: https://modelcontextprotocol.io/

## Modules

| Module | What it covers | Upstream dependency | Requirements | Repo |
| --- | --- | --- | --- | --- |
| **CompTox MCP** | Identity, hazard, exposure | EPA CompTox API | **API key required** (`CTX_API_KEY`) | https://github.com/ToxMCP/comptox-mcp |
| **ADMETlab MCP** | Rapid ADMET prediction + utilities | ADMETlab 3.0 API | No key by default (upstream may rate-limit) | https://github.com/ToxMCP/admetlab-mcp |
| **AOP MCP** | Mechanistic pathways + authoring workflows | AOP-Wiki / AOP-DB / federation | Internet access recommended | https://github.com/ToxMCP/aop-mcp |
| **O-QT MCP** | OECD QSAR Toolbox workflows + reports | OECD QSAR Toolbox WebAPI | Requires QSAR Toolbox WebAPI access | https://github.com/ToxMCP/oqt-mcp |
| **PBPK MCP** | PBPK simulation control + PK analytics | Open Systems Pharmacology Suite | Local engine setup (see repo) | https://github.com/ToxMCP/pbpk-mcp |

### Which one should I try first?

- If you want the **lowest-friction first run**, start with **ADMETlab MCP**.
- If you want the most **on-brand toxicology dataset integration**, start with **CompTox MCP** (you’ll need an API key).

## Notes

- Each MCP server is versioned and released independently.
- Some modules depend on proprietary or rate-limited upstream services—check each module README for exact setup.

## Acknowledgements / Origins

ToxMCP was developed in the context of the **VHP4Safety** project (see: https://github.com/VHP4Safety) and related research/engineering efforts.

This suite integrates with third-party data sources and services (e.g., EPA CompTox, ADMETlab, AOP resources, OECD QSAR Toolbox, Open Systems Pharmacology). Those upstream resources are owned and governed by their respective providers; users are responsible for meeting any access, API key, rate limit, and license/EULA requirements described in each module.

## License

Apache-2.0

## Cite

If you use ToxMCP in your work, please cite the preprint: https://doi.org/10.64898/2026.02.06.703989

Citation metadata: [CITATION.cff](./CITATION.cff)
