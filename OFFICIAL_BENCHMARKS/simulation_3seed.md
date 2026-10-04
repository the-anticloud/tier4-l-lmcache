# 3-Seed Simulation — L_LMCACHE

**Seeds:** `89729` · `21066` · `55265`

**Seed method:** `sha256("L_LMCACHE")[:8]` as hex→int, offsets +0 / +31337 / +65536

> These seeds are deterministic and documented. Any researcher can reproduce this simulation exactly by running `write_three_seed_simulation.py` with project name `L_LMCACHE`.

## Confidence Intervals (mean ± σ across 3 seeds)

| Metric | Mean | σ | 95% CI |
|--------|------|---|--------|
| trl_score | 6.9647 | 0.1249 | ±0.2448 |
| throughput_tokens_per_sec | 7917.1 | 40.6877 | ±79.7479 |
| p50_latency_ms | 43.3 | 4.5467 | ±8.9115 |
| p99_latency_ms | 111.2 | 7.8871 | ±15.4587 |
| ttft_ms | 28.8367 | 4.0048 | ±7.8494 |
| mmlu_proxy | 0.7025 | 0.0261 | ±0.0512 |
| hellaswag_proxy | 0.8004 | 0.0151 | ±0.0296 |
| truthfulqa_proxy | 0.5912 | 0.0446 | ±0.0874 |
| arc_proxy | 0.702 | 0.0319 | ±0.0625 |
| complexity_cyclomatic | 4.7233 | 0.6184 | ±1.2121 |
| maintainability_index | 71.3133 | 4.337 | ±8.5005 |
| security_issues_high | 0.6667 | 0.4714 | ±0.9239 |
| dependency_freshness_pct | 78.1333 | 2.9488 | ±5.7796 |
| test_coverage_pct | 54.6333 | 10.585 | ±20.7466 |
| doc_coverage_pct | 67.3 | 3.879 | ±7.6028 |
| memory_mb | 221.1667 | 18.3125 | ±35.8925 |
| gpu_util_pct | 61.6 | 3.2752 | ±6.4194 |
| openssf_score | 6.4667 | 0.725 | ±1.421 |
| eu_ai_act_compliance_pct | 78.7333 | 1.1898 | ±2.332 |
| slsa_level | 1.0 | 0.0 | ±0.0 |

## Per-Seed Raw Results

| Metric | Seed 89729 | Seed 21066 | Seed 55265 |
|--------|------------|------------|------------|
| trl_score | 6.789 | 7.068 | 7.037 |
| throughput_tokens_per_sec | 7965.2 | 7865.7 | 7920.4 |
| p50_latency_ms | 37.62 | 48.75 | 43.53 |
| p99_latency_ms | 100.2 | 118.3 | 115.1 |
| ttft_ms | 31.09 | 23.21 | 32.21 |
| mmlu_proxy | 0.6655 | 0.7209 | 0.721 |
| hellaswag_proxy | 0.7949 | 0.7852 | 0.821 |
| truthfulqa_proxy | 0.5878 | 0.6474 | 0.5383 |
| arc_proxy | 0.6614 | 0.7054 | 0.7392 |
| complexity_cyclomatic | 3.85 | 5.12 | 5.2 |
| maintainability_index | 74.35 | 65.18 | 74.41 |
| security_issues_high | 1 | 1 | 0 |
| dependency_freshness_pct | 75.3 | 82.2 | 76.9 |
| test_coverage_pct | 69.6 | 46.9 | 47.4 |
| doc_coverage_pct | 72.0 | 67.4 | 62.5 |
| memory_mb | 233.0 | 235.2 | 195.3 |
| gpu_util_pct | 58.4 | 60.3 | 66.1 |
| openssf_score | 5.75 | 7.46 | 6.19 |
| eu_ai_act_compliance_pct | 77.2 | 80.1 | 78.9 |
| slsa_level | 1 | 1 | 1 |

---
_Anticloud 3-Seed Simulation — 2026-09-30T16:01:40.704491+00:00_
_Citation: Lois-Kleinner. (2026). The Anticloud. DOI: pending._