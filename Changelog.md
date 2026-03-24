# Debian 13 CIS

## March 2026 — audit alignment

- Removed CIS v8-only markers from audit YAML where present (`remove_cisv8_from_audit.py`)
- Added YAML document headers (`---`) to `goss.yml`, `standalone.yml`, and `vars/CIS.yml`
- Aligned Goss titles and `CIS_ID` values with `v1.0.0_recommedations.json`; corrected several mis-keyed section 2 / 3 / 5 audit files
- Spelling: `dependancy` → `dependency` in `vars/CIS.yml`
- New helper: `scripts/sync_audit_yaml_titles_from_json.py` (path-based rule IDs, including `cis_*.*.x` layouts)

# 1.0.0 - Initial
