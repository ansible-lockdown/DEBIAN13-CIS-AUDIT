# Debian 13 CIS

## March 2026 — audit alignment

- Removed CIS v8-only markers
- Added YAML document headers (`---`) to `goss.yml`, `standalone.yml`, and `vars/CIS.yml`
- Aligned Goss titles and `CIS_ID` values
- corrected several mis-keyed section 2 / 3 / 5 audit files
- Spellings
- variable naming aligned with remediate
  - deb13cis_gui variable renamed to deb13cis_desktop_required
  - deb13cis_time_pool_name to deb13cis_time_pool
  - deb13cis_syslog_server to deb13cis_system_is_log_server

# 1.0.0 - Initial
