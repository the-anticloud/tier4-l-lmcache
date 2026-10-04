# Deploy Guide — L_LMCACHE
**Tier:** TIER_4_INFERENCE_AGENTS | **Stack:** Python 3.11, PyTorch 2.10+, shared memory, mmap, CUDA IPC, AIOSS_FORMAT
**Air-gap capable after initial setup.**

## Prerequisites
Python 3.11+, PyTorch 2.10+, CUDA 12.x, T4 GPU. mmap for disk-resident cache.

## Environment
T4 GPU. VRAM for KV cache: ~2GB per 2K-token prefix. 32GB RAM for disk-resident cache.

## AIOSS Integration
```bash
aioss init --module L_LMCACHE --output ./l_lmcache.aioss
aioss append --chain ./l_lmcache.aioss --payload ./output.bin --module L_LMCACHE
aioss verify --chain ./l_lmcache.aioss
```

## Air-Gap Setup
```bash
pip download -r requirements.txt -d ./wheels/
pip install --no-index --find-links ./wheels/ -r requirements.txt
```

## PAX 27B Harness Wiring
```python
from anticloud_pax import PAXHarness
harness = PAXHarness(
    model_path="./pax-27b-q4.gguf",
    module="L_LMCACHE",
    aioss_chain="./L_LMCACHE.aioss",
    classification="L5_NARROW_L2_GENERAL"
)
result = harness.process(input_data)
```

## Verification
```bash
aioss verify --chain ./L_LMCACHE.aioss --verbose
python -m L_LMCACHE.tests.smoke
```
