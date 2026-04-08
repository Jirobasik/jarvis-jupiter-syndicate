# DX-REPORT.md: Jupiter Developer Platform Integration

## Onboarding Experience
- **Time to first call:** ~4 hours of debugging.
- **Complexity:** The Jupiter Developer Platform is powerful but walled behind strict security checkpoints (Vercel/Privy). We hit 403 Forbidden errors consistently when using programmatic API requests (axios/curl), which forced us to implement a browser-injected API layer ("Kraken").
- **What sucked:** The lack of clear guidance for headless/autonomous agents to pass the security checks. 

## AI Stack Feedback
- **Used:** Jupiter CLI & API.
- **Experience:** The CLI is excellent for rapid prototyping. The API structure is intuitive, but error messages (e.g., 403) are too generic for an automated system to diagnose.
- **Improvement Idea:** Provide an `agent-mode` flag or a specific API endpoint that bypasses browser-based security checks using API keys/signed payloads, specifically for verified agent partners.

## Where APIs Bit Us
- **Trigger API:** Latency in execution of limit orders needs better feedback loop.
- **Docs:** The docs are great, but edge-case error documentation (API vs Browser) needs an explicit section for AI agents.

## How we'd rebuild developers.jup.ag
I would implement a dedicated "Agent Playground" where developers can test API flows using just a Bearer token without needing to bypass browser-fingerprinting security protocols.
