# Nora product boundary

Status: architecture decision, 2026-11-04. This describes the intended separation, not a completed audit of the private local Nora runtime.

Nora is Microkosm Labs' independent, local-first AI assistant. Nora owns conversational UX, reasoning, personality, context, interpretation and recommendations. Nora does not own infrastructure execution policy, credential brokerage, tunnel management, generic health monitoring, or automatic service recovery.

Taxi Driver is a separate, optional operations platform. Nora can request tool operations over an authenticated, authorized MCP connection, then explain returned evidence. Taxi Driver enforces the permissions in code; Nora's prompts cannot grant authority. Nora must continue to function when Taxi Driver is absent.

A service called Nora can be registered as an ordinary monitored target in Taxi Driver. Taxi Driver must not require Nora, and Nora must not be the only supported client.

## Audit required before migration

- Review Nora's local runtime, launchers and private documentation for MCP tunnel startup, shell execution, service recovery, embedded tokens and hardcoded Taxi Driver dependencies.
- Keep Nora-specific model, memory, persona and UX code in Nora; migrate only generic operations code to Taxi Driver after dependency mapping and secret review.
- Verify independent startup and graceful tool-unavailable behavior.
- Do not move private memory, secrets, prompts or operational databases into this public repository.
- Do not assume the public site repository contains the entire local Nora implementation.

See [Taxi Driver's product boundary](https://github.com/tholmberg/taxi-driver-mcp/blob/main/docs/independent-products-boundary.md) for the complementary operations contract (link will resolve after that document is merged).
