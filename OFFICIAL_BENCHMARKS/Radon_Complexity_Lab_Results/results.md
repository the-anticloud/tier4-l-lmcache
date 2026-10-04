# Radon_Complexity_Lab_Results
**Project:** `L_LMCACHE` | **Status:** `PASS` | **Run:** `2026-09-30T17:14:20.030944+00:00`

**Framework:** [Radon — Cyclomatic Complexity & Maintainability Index](https://radon.readthedocs.io/)

## Key Metrics

- **files_analyzed:** `10`
- **average_complexity:** `{'grade': 'A', 'score': 2.3333333333333335}`
- **complexity_grade:** `A`
- **complexity_score:** `2.3333333333333335`
- **mi_output:** `E:\fenta\Downloads\The Anticloud\TIER_4_INFERENCE_AGENTS\L_LMCACHE\UPSTREAM\setup.py - A (65.57)
E:\fenta\Downloads\The `

## Raw Output (first 50 lines)
```
E:\fenta\Downloads\The Anticloud\TIER_4_INFERENCE_AGENTS\L_LMCACHE\UPSTREAM\setup.py
    F 29:0 _read_requirements - A (5)
    F 40:0 _load_proto_generator - A (3)
    C 62:0 _BuildPyWithGrpcStubs - A (3)
    M 65:4 _BuildPyWithGrpcStubs.run - A (2)
E:\fenta\Downloads\The Anticloud\TIER_4_INFERENCE_AGENTS\L_LMCACHE\UPSTREAM\lmcache\banner.py
    F 66:0 _render_banner - B (8)
    F 104:0 print_banner_once - A (3)
    F 61:0 _banner_disabled - A (1)
E:\fenta\Downloads\The Anticloud\TIER_4_INFERENCE_AGENTS\L_LMCACHE\UPSTREAM\lmcache\connections.py
    M 28:4 HTTPConnection.get_sync_client - A (3)
    M 36:4 HTTPConnection.get_async_client - A (3)
    C 17:0 HTTPConnection - A (2)
    M 42:4 HTTPConnection._validate_http_url - A (2)
    M 53:4 HTTPConnection.get_response - A (2)
    M 73:4 HTTPConnection.get_async_response - A (2)
    M 138:4 HTTPConnection.download_file - A (2)
    M 155:4 HTTPConnection.async_download_file - A (2)
    M 20:4 HTTPConnection.__init__ - A (1)
    M 50:4 HTTPConnection._headers - A (1)
    M 87:4 HTTPConnection.get_bytes - A (1)
    M 93:4 HTTPConnection.async_get_bytes - A (1)
    M 104:4 HTTPConnection.get_text - A (1)
    M 110:4 HTTPConnection.async_get_text - A (1)
    M 121:4 HTTPConnection.get_json - A (1)
    M 127:4 HTTPConnection.async_get_json - A (1)
E:\fenta\Downloads\The Anticloud\TIER_4_INFERENCE_AGENTS\L_LMCACHE\UPSTREAM\lmcache\logging.py
    C 17:0 CustomFormatter - A (3)
    F 66:0 init_logger - A (2)
    M 33:4 CustomFormatter._
```

---
_Anticloud Independent Benchmark — 2026-09-30T17:14:20.030944+00:00_