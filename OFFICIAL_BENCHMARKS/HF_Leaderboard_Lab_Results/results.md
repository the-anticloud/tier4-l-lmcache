# HF_Leaderboard_Lab_Results

**Project:** `L_LMCACHE`  
**Tier:** `TIER_4_INFERENCE_AGENTS`  
**Slug:** `LMCache/LMCache`  
**Commit:** `0f166d0bcf5e`  
**Run:** `2026-09-30T15:07:07.146295+00:00`  

## Isolation Environment

| Field | Value |
| ----- | ----- |
| Platform | `win32` |
| Python | `3.12.10` |
| HF model | `distilbert-base-uncased` |
| HF load time | `4.42s` |
| Inference device | `cpu` |

## Results

**Framework:** [HuggingFace Open LLM Leaderboard (proxy via distilbert-base-uncased)](https://huggingface.co/docs/leaderboards/en/open_llm_leaderboard/archive)

**Model used:** `distilbert-base-uncased`

### Inference Latency (Classification)

| Metric | Value |
| ------ | ----- |
| Avg latency | **51.12 ms** |
| Min latency | 47.07 ms |
| Max latency | 59.0 ms |
| Samples | 5 |

### Real Tokenization Results

| Field | Value |
| ----- | ----- |
| Token count | **43** |
| Tokenization latency | 0.0 ms |
| Classification label | `LABEL_0` |
| Classification score | 0.5878 |
| Classification latency | 76.96 ms |
| Status | **PASS** |

**Input text tokenized:**
```
L_LMCACHE (LMCache/LMCache) — 2610 files, 479768 source lines, licence Apache-2.0, primary language ['Python']
```

**First 20 tokens:**
```
['[CLS]', 'l', '_', 'l', '##mc', '##ache', '(', 'l', '##mc', '##ache', '/', 'l', '##mc', '##ache', ')', '—', '261', '##0', 'files', ',']
```

> Full MMLU/HellaSwag/TruthfulQA/ARC/Winogrande/GSM8K require dedicated GPU.
> These results are CPU inference proxy metrics using distilbert-base-uncased.

---
_Anticloud Benchmark Suite — isolation log — 2026-09-30T15:07:07.146295+00:00_