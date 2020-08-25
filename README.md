# psu-apply

Ansible role to apply Oracle quarterly patches (PSU) to single instance (SI) and RAC instances.


## Role Variables

### vars/main.yml

* psu:  dictionary variable with latest PSU information for 12.1.0.2 and 11.2.0.4

* opatch: dictionary variable with latest opatch version for 12.1.0.2 and 11.2.0.4



### defaults/main.yml

* `patch_name: JUL2019`  # Should match quarterly_patches dictionary variable defined in vars/main.yml


### Required Inventory Variables

* `oracle_install_type`: valid values are `si`, `rac`, or `si_asm`.  Used to determine if host is a single instance database install, RAC cluster, or Single Instance Oracle Restart.

* oracle_stage_install: directory that contains all oracle install files

* oracle_stage: directory to store logs and scripts used during playbook execution.

* oracle_version: expects values of 11.2.0.4 or 12.1.0.2

### Optional Inventory Variables
* oneoff_patches: dictionary variable with list of one-off patches to apply for 12.1.0.2 and 11.2.0.4
Example `oneoff_patches` variable definition:

```
oneoff_patches:
  11.2.0.4.180116:
    - patchid: 16792070   # ORA-07445: [KKQSTARTEMPCOLREW()+857] WHEN 10053 TRACING ENABLED
      filename: p16792070_112040_Linux-x86-64.zip
    - patchid: 20762867   # ORA-600 [KKFI.QBCVFR] HIT IN COMPLEX QUERY AT WHICH FBI ARE INVOLVED
      filename: p20762867_112040_Linux-x86-64.zip
    - patchid: 19428389   # ORA-00600:[KOPUUPKL1] SELECTING FROM DBA_SCHEDULER_JOB_ARGS
      filename: p19428389_112040_Linux-x86-64.zip
```

* agent_home: path to EM Agent home directory (ie /app/oracle/agent12c/agent_inst)

## Adding New Patch
* Download Patch and save to shared location.
* Download latest versio of Opatch and save to shared location.
* In `vars.yml`
  * Update OPatch version in `opatch:` variable
  * Add new patch to `quarterly_patches:` variable


## Example Playbook

```
- role: ansible-oracle-psu
  vars:
    oracle_version: 19.0.0
    patch_name: JUL2019
    patch_type: ru
  tags: ansible-oracle-psu

- role: ansible-oracle-psu
  vars:
    oracle_version: 12.1.0.2
    patch_name: JUL2017
    patch_type: dbbp
  tags: ansible-oracle-psu

- role: ansible-oracle-psu
  vars:
    oracle_version: 11.2.0.4
    patch_name: JAN2018
    patch_type: psu
  tags: 11g-psu
```
