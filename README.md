# ViaFabricPlus Bedrock — Legacy compatibility track

This branch exists to document compatibility with the `ViaFabricPlus Legacy` branch for Minecraft 1.21.11.

## Important: no separate addon JAR is required for 1.21.11

ViaFabricPlus Legacy keeps the Bedrock integration in its host mod and updates it to **ViaBedrock 0.0.32 / Bedrock 1.26.60**, with Cloudburst NetherNet transport. The implementation lives in the host fork's source tree so it can use the 1.21.11-specific connection hooks; this repository tracks the compatibility target and must not ship a duplicate addon JAR.

For Minecraft 1.21.11:

1. Install [ViaFabricPlus Legacy](https://github.com/Namnarak/ViaFabricPlus/tree/legacy/1.21.11-26.3).
2. Do **not** install this repository as a second mod. The newer standalone addon is not binary-compatible with ViaFabricPlus 4.4.15.
3. Use the Bedrock protocol selection built into ViaFabricPlus Legacy. The current source/build is maintained on the [legacy/1.21.11-26.3 branch](https://github.com/Namnarak/ViaFabricPlus/tree/legacy/1.21.11-26.3).

## Why this branch does not publish an addon

The current standalone addon targets:
- ViaFabricPlus 5.1.3 or newer
- Minecraft 26.3
- Java 25+

Its entrypoint and API calls target the newer ViaFabricPlus addon API. The 1.21.11 / 4.4.15 line uses a different integration API and already bundles Bedrock support. Reusing the current JAR on that branch would be an invalid compatibility claim.

## Compatibility matrix

| Host mod line | Minecraft client | Bedrock implementation | Separate addon |
|---|---:|---|---|
| ViaFabricPlus Legacy 4.4.15 + ViaBedrock 0.0.32 | 1.21.11 | Bundled NetherNet integration (Bedrock 1.26.60) | No |
| ViaFabricPlus 5.1.3+ | 26.3 | Standalone addon | Yes |

This compatibility line intentionally does not publish a second mod JAR: the Bedrock integration is built into ViaFabricPlus Legacy and shares its 1.21.11 connection hooks.

