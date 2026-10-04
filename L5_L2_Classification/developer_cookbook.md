# Developer Cookbook — L_LMCACHE
**Stack:** Python 3.11, PyTorch 2.10+, shared memory, mmap, CUDA IPC, AIOSS_FORMAT
**Domain:** LMCache: KV-cache sharing across requests and sessions for PAX 27B throughput optimization

## Pre-compute and cache system prompt
```python
from l_lmcache import LMCache

cache = LMCache(
    pax_model="./pax-27b-q4.gguf",
    cache_dir="./lm_cache/",
    aioss_chain="./lmcache.aioss"
)

# Pre-compute KV cache for Anticloud system prompt
cache.precompute_prefix(
    name="anticloud_clinical",
    text="You are a sovereign clinical AI assistant. All outputs are HIPAA-compliant. "
         "You only use information from the local Anticloud corpus..."
)

# Inference reuses cached prefix — fast first token
result = cache.generate_with_prefix(
    prefix_name="anticloud_clinical",
    user_message="Analyze this ECG for arrhythmia",
    max_tokens=256
)
print(f"TTFT: {result.time_to_first_token_ms:.0f}ms (vs {result.baseline_ttft_ms:.0f}ms without cache)")
```

## Cross-session cache sharing
```python
cache.share_prefix("anticloud_clinical", sessions=["session_001", "session_002"])
```

## Cache stats
```python
stats = cache.stats()
print(f"Hit rate: {stats.hit_rate:.1%}, VRAM saved: {stats.vram_saved_mb:.0f}MB")
```

## AIOSS Chain Append
```python
import hashlib, time

def aioss_append(chain_path, payload: bytes, module_id: str):
    entry_hash = hashlib.sha3_256(payload).digest()
    ts = int(time.time_ns()).to_bytes(8, 'big')
    with open(chain_path, 'rb') as f:
        f.seek(-32, 2); prev_hash = f.read(32)
    new_hash = hashlib.sha3_256(prev_hash + entry_hash + ts).digest()
    with open(chain_path, 'ab') as f:
        f.write(ts + entry_hash + new_hash)
    return new_hash.hex()
```
