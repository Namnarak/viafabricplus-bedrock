# ViaFabricPlus Bedrock — Legacy compatibility track

This branch exists to document compatibility with the `ViaFabricPlus Legacy` branch for Minecraft 1.21.11.

## Important: no separate addon JAR is required for 1.21.11

Upstream ViaFabricPlus 4.4.15 already includes its Bedrock Edition integration (ViaBedrock, Bedrock connection pipeline, settings and Realms support) in the main mod. The legacy build keeps that integrated implementation.

For Minecraft 1.21.11:

1. Install [ViaFabricPlus Legacy](https://github.com/Namnarak/ViaFabricPlus/tree/legacy/1.21.11-26.3).
2. Do **not** install this repository as a second mod. The newer standalone addon is not binary-compatible with ViaFabricPlus 4.4.15.
3. Use the Bedrock protocol selection built into ViaFabricPlus Legacy.

## Why this branch does not publish an addon

The current standalone addon targets:
- ViaFabricPlus 5.1.3 or newer
- Minecraft 26.3
- Java 25+

Its entrypoint and API calls target the newer ViaFabricPlus addon API. The 1.21.11 / 4.4.15 line uses a different integration API and already bundles Bedrock support. Reusing the current JAR on that branch would be an invalid compatibility claim.

## Compatibility matrix

| Host mod line | Minecraft client | Bedrock implementation | Separate addon |
|---|---:|---|---|
| ViaFabricPlus Legacy 4.4.15 | 1.21.11 | Bundled in ViaFabricPlus | No |
| ViaFabricPlus 5.1.3+ | 26.3 | Standalone addon | Yes |

The next step for a true standalone 1.21.11 addon would be a source-level port against the 4.4.15 addon entrypoint/API, followed by a dedicated build and runtime test. This branch intentionally does not ship a non-working JAR.

