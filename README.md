Spectre / Metdown checker
=========

Install a script to check [spectre]/[meltdown] vulnerabilities.

Requirements
------------

There is no requirements

Role Variables
--------------

```yaml
spectre_meltdown_check_disabled: true
```


Dependencies
------------

There is no dependencies

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
  - { role: SimpliField.spectre-meltdown-checker }
```

To run by variant

```yaml
- hosts: servers
  roles:
  - { role: SimpliField.spectre-meltdown-checker }

- hosts: servers
  tasks:
  - name: check for spectre/meltdown variant 1
    shell: spectre-meltdown-checker --variant 1 > /dev/null
    register: spectre_meltdown_checker_result
    changed_when: false
    failed_when: spectre_meltdown_checker_result.rc != 0
    tags:
    - spectre
    - meltdown
  - name: check for spectre/meltdown variant 2
    shell: spectre-meltdown-checker --variant 2 > /dev/null
    register: spectre_meltdown_checker_result
    changed_when: false
    failed_when: spectre_meltdown_checker_result.rc != 0
    tags:
    - spectre
    - meltdown
  - name: check for spectre/meltdown variant 3
    shell: spectre-meltdown-checker --variant 3 > /dev/null
    register: spectre_meltdown_checker_result
    changed_when: false
    failed_when: spectre_meltdown_checker_result.rc != 0
    tags:
    - spectre
    - meltdown
```

License
-------

BSD

[spectre](https://spectreattack.com/)
[meltdown](https://meltdownattack.com/)
