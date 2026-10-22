# Issues Found

| Issue | Type | Line(s) | Description | Fix Approach |
|-------|------|---------|-------------|--------------|
| os.system with joined string (B605) | Security (High) | ~49 | Command built from input allows command injection | Use subprocess.run with a list, no shell |
| tempfile.mktemp (B306) | Security (Medium) | ~44 | Predictable temp file name causes a race condition | Use NamedTemporaryFile |
| Hardcoded password (B105) | Security (Low) | 5 | Password stored in source code | Removed, since it was unused |
| assert for validation (B101) | Security (Low) | ~19 | Asserts are stripped under python -O | Raise ValueError |
| Mutable default notes=[] (W0102) | Bug | ~18 | The list is shared across all calls | Default None, create the list inside |
| Broad except Exception (W0718) | Bug | ~39 | Hides real errors | Catch KeyError only |
| camelCase names (C0103) | Style | many | Not PEP 8 | Renamed to snake_case |
| Missing docstrings (C0114, C0116) | Style | many | No documentation | Added docstrings |
| Spacing and long lines (E225, E261, E303, E501) | Style (Flake8) | various | PEP 8 formatting errors | Reformatted |