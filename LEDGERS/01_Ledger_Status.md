# Ledger Status

**Project:** `L_LMCACHE`  
**Tier:** TIER_4_INFERENCE_AGENTS  
**Identity:** Upstream `LMCache/LMCache` @ `0f166d0bcf5e` (Apache-2.0)

## Chain state

| Fact | Value |
| --- | --- |
| Upstream | `LMCache/LMCache` |
| Commit | `0f166d0bcf5e5526f861610e5b7b9a098595556e` |
| Upstream licence | Apache-2.0 |
| Licence class | permissive |
| Clone size | 27.64 MB |
| Ledger | 0 blocks, chain verified |
| Current TRL | NOT YET MEASURED |
| Post-optimisation TRL | NOT YET MEASURED |
| II budget cap | 1000.0 IIU |
| Verified upstream edits | 1 |

- Blocks: **0**
- Head digest: `None`
- Chain verification: **verified**

## Independent verification

The chain is verifiable without trusting this project's tooling:

```
anticloud ledger verify
anticloud ledger export > ledger.jsonl
```

Each block carries the previous block's digest, so removing or reordering an
entry invalidates every block after it. That property is the reason the
ledger can stand in for a claim of what happened.
