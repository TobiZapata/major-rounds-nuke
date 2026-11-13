# Major rounds: Nuke

Versioned replay data for the Major MVP CS simulator.

`v1.0.0` contains 981 eligible Nuke rounds from 49 unique demos (51 source
files), sampled at 8 Hz plus action ticks. Of these, 888 rounds have equipment
supported by the assembler and matching derived metrics and resolutions.

## Files

- `v1.0.0/index.json`: eligible round catalog.
- `v1.0.0/economy-index.json`: catalog with equipment evidence and compatibility.
- `v1.0.0/round-metrics-v1.json.gz`: derived player metrics.
- `v1.0.0/round-resolution-v1.json.gz`: resolution-time statistics and equipment.
- `v1.0.0/demos/<sha256>/rNNN.json.gz`: compressed per-round telemetry.

Published root: https://tobizapata.github.io/major-rounds-nuke/v1.0.0/

Catalog references keep the application prefix `/round-bank-nuke/`. Consumers
map that prefix to this fixed Pages root and load selected rounds on demand.
The version directory and Git tag are immutable. Publish changed banks under
a new version and preserve older versions for saved games.

## Provenance

The laboratory classified 1,043 rounds; 62 were excluded from this published
bank. Reasons include incomplete postround tails, friendly fire, world deaths
and missing opening weapons. A round can have more than one exclusion reason.
Duplicate source files are deduplicated by SHA-256, not their names.

Catalogs retain source demo filenames, hashed demo IDs, Steam IDs, round timing
and results. Replays contain positions, inventories and events needed for
playback. Original `.dem` files are not uploaded. This repository does not
assert ownership of the matches, demos or third-party identities; the source
material's attribution and redistribution terms still apply.

All replay checksums, end-state actor totals and inventories were validated
before import. The bank uses demoparser2 0.42.2. The extraction assumes 64 ticks/s;
buy labels describe weapon composition rather than money spent or player intent.
