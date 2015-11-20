# psu-apply

Ansible role to apply Oracle quarterly patches (PSU) to single instance (SI) and RAC instances.


## Role Variables

### vars/main.yml

* psu:  dictionary variable with latest PSU information for 12.1.0.2 and 11.2.0.4

* opatch: dictionary variable with latest opatch version for 12.1.0.2 and 11.2.0.4

* oneoff_patches: dictionary variable with list of one-off patches to apply for 12.1.0.2 and 11.2.0.4

### Required Inventory Variables

* oracle_install_type: valid values are SI or RAC.  Used to determine if host is a single instance database install or part of a RAC cluster.

* oracle_stage_install: directory that contains all oracle install files

* oracle_stage: directory to store logs and scripts used during playbook execution.

* oracle_version: expects values of 11.2.0.4 or 12.1.0.2

### Optional Inventory Variables

* agent_home: path to EM Agent home directory (ie /app/oracle/agent12c/agent_inst)


## Example Playbook

    - hosts: servers
      roles:
         - role: psu-apply
