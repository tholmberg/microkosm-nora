# Microkosm Nora

**Nora is Microkosm Labs' independent local-first AI assistant.** Nora owns conversation, reasoning, personality, context and recommendations. It is not Taxi Driver's operations control center.

Taxi Driver is a **separate, optional operations platform** that Nora may use through authenticated and authorized MCP tools. Nora must remain usable without Taxi Driver; Taxi Driver must operate without Nora. The AI cannot grant itself operational permissions.

See [Nora's product boundary and migration audit](docs/product-boundary.md).

## Repository scope

This repository currently contains the **public Nora project site**, not a complete copy of Nora's private local runtime. Railway serves the static site with Nginx using the included Dockerfile. Do not confuse deployment of this marketing site with deployment of Nora's assistant runtime.

Local runtime coupling, launchers, and private code still require an audit before claiming the products are fully separated.
