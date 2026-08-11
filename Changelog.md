# Debian 13 CIS

## Based on CIS v1.0.0 - Branch align_1.0.0

- Corrected 12 files gated on the wrong `deb13cis_rule_*` toggle, which silently disabled the neighbouring control's check: 1.1.2.6.4, 1.1.2.7.4, 2.1.7, 2.1.15, 2.1.21, 2.1.22, 2.1.23, 2.4.1.9, 3.2.3, 3.2.5, 3.2.6, 5.3.3.3.3
- Corrected the 1.7.10 / 1.7.11 GDM config path `/etc/gdm/custom.conf` -> `/etc/gdm3/custom.conf`, the path remediation actually writes on Debian
- Corrected the 6.3.3 AIDE config path `/etc/aide.conf` -> `/etc/aide/aide.conf` and the five audit tool paths `/sbin/*` -> `/usr/sbin/*`, matching remediation
- Removed 6 unreferenced ssh algorithm lists from vars/CIS.yml - no goss test consumed them and their names had drifted from the remediation `sshd_`-prefixed equivalents
- Aligned `deb13cis_legacy_boot` and `deb13cis_set_boot_pass` to the remediation defaults (false); as `true` they produced false failures in standalone audit runs
- Added CONTRIBUTING.rst (was missing) and replaced the stub .gitignore with the standard Lockdown set
- Fixed inverted 2.1.22 gate - the check only ran when the host *was* a mail server, the opposite of the remediation condition, so it never ran on a normal host
- Fixed 2.1.22 file resource path `/etc/postfix/main.conf` -> `/etc/postfix/main.cf`, the file the remediation actually writes
- Removed orphan `section_6/cis_6.1.1.1.x/cis_6.1.1.4.yml` - filename ID does not exist in v1.0.0, it reused the 6.1.1.1.4 toggle for an unrelated syslog-service check with no remediation counterpart
- Corrected the 2.1.22 title - wrong leading ID (2.1.21), missing separator, and singular "agent" where the benchmark says "agents are"

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
