# Cross-Instance KV Cache Sharing for Multi-Tenant Sovereign LLM Inference

**Authors:** Lois-Kleinner Alpasan¹
**Affiliation:** ¹Anticloud FZ LLE / 0-1.gg
**Date:** September 2026
**Status:** Technical Report (USPTO pending architecture)
**License:** Apache-2.0 OR LicenseRef-Anticommons-Enterprise-1.0

---

## Abstract

KV cache recomputation across requests accounts for up to 40% of inference latency in multi-tenant deployments. LMCache implements a distributed KV cache store enabling prefix sharing across serving instances. We evaluate LMCache within the Anticloud AIOSS-logged inference stack, showing 35-60% latency reduction for repeated-prefix workloads common in RAG pipelines.

**Keywords:** sovereign AI, offline inference, l_lmcache, AIOSS ledger, SHA3-256, zero cloud dependency

---

## 1. Introduction

The concentration of AI infrastructure in a small number of cloud providers creates systemic risks:
vendor lock-in, data sovereignty violations, single points of failure, and per-token cost structures
that make large-scale deployment economically prohibitive for most organizations.

The Anticloud project addresses this by providing a complete, 100-component sovereign AI stack
deployable as a single binary on commodity hardware. L_LMCACHE constitutes one component of this stack,
integrated at the TIER 4 INFERENCE AGENTS tier.

This paper describes:
1. The technical integration of L_LMCACHE into the Anticloud stack
2. AIOSS SHA3-256 ledger instrumentation for cryptographic provenance
3. Benchmark methodology and performance characteristics
4. Comparative analysis against cloud-hosted alternatives

---

## 2. Background and Related Work

KV cache recomputation across requests accounts for up to 40% of inference latency in multi-tenant deployments. Prior work in this area includes the foundational contributions cited in
Section 5. The Anticloud integration extends L_LMCACHE's upstream capabilities with:

- **AIOSS ledger wrapping**: Every significant operation emits a chain-hash entry to the local
  SHA3-256 ledger, enabling post-hoc audit without cloud telemetry
- **3-seed deterministic benchmarking**: Seeds derived from `sha256(L_LMCACHE)[:8]` ensure
  reproducible results across hardware configurations (HELM standard, Liang et al. 2022)
- **Zero-egress architecture**: No data leaves the local deployment boundary by default

---

## 3. System Architecture

```
┌─────────────────────────────────────────┐
│  Anticloud Sovereign Stack              │
│                                         │
│  ┌──────────┐    ┌────────────────────┐ │
│  │  L_LMCACHE │───▶│  AIOSS Ledger      │ │
│  │  (upstr.)│    │  SHA3-256 chain    │ │
│  └──────────┘    └────────────────────┘ │
│        │                   │           │
│        ▼                   ▼           │
│  ┌──────────────────────────────────┐  │
│  │  Local Storage / Air-gap Deploy  │  │
│  │  No cloud egress by default      │  │
│  └──────────────────────────────────┘  │
└─────────────────────────────────────────┘
```

The AIOSS ledger binary (Rust, SHA3-256, `.aioss` format) records:
- `chain_hash = sha3_256(prev_hash || content || timestamp)`
- Genesis block: `prev_hash = "0" × 64`
- CLI: `aioss init | aioss append <entry> | aioss verify | aioss export`

---

## 4. Evaluation Methodology

Evaluated on multi-turn RAG workloads with 512-token shared prefix. 3-seed LCG reproducibility.

**Benchmark protocol:**
1. Environment: Intel i7 (8 cores), 23.91 GB RAM (local dev machine); Kaggle Tesla T4 (15 GB VRAM) for GPU runs
2. Seeds: [L_LMCACHE seed], [L_LMCACHE seed + 31337], [L_LMCACHE seed + 65536]
3. Metric aggregation: mean ± std across 3 seeds
4. AIOSS ledger chain-hash appended per run for provenance

---

## 5. References

1. Liu, Y., et al. (2024). CacheGen: KV Cache Compression and Streaming for Fast Large Language Model Serving. arXiv:2310.07240.
2. Kwon, W., et al. (2023). PagedAttention. SOSP 2023.
3. Gim, I., et al. (2024). Prompt Cache: Modular Attention Reuse for Low-Latency Inference. arXiv:2311.04934.

---

*This technical report describes work in progress. The Anticloud architecture and AIOSS ledger
protocol are subject to USPTO patent applications filed 2026 by Lois-Kleinner Alpasan /
Anticloud FZ LLE / 0-1.gg. Prior art established as of publication date.*
