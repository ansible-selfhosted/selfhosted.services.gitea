[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Copier](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/copier-org/copier/master/img/badge/badge-grayscale-inverted-border.json)](https://github.com/copier-org/copier)
[![Podman Badge](https://img.shields.io/badge/Podman-892CA0?logo=podman&logoColor=white)](https://podman.io/)
[![Hatch project](https://img.shields.io/badge/%F0%9F%A5%9A-Hatch-4051b5.svg)](https://github.com/pypa/hatch)
![CI](https://github.com/ansible-selfhosted/selfhosted.services.gitea/actions/workflows/ci.yml/badge.svg)
[![Ansible](https://img.shields.io/badge/Ansible-Molecule-EE0000?style=plastic&logo=ansible&logoColor=white)](https://github.com/ansible/molecule)

<!-- BEGIN_ANSIBLE_DOCS -->

# Ansible Role: [gitea](https://docs.gitea.com/)

A role to deploy Gitea using rootless Podman with systemd.

## Role Requirements

- none

*Refer to services collection for general requirements*

## Role Arguments

|Option|Description|Type|Required|Default|choices|
|---|---|---|---|---|---|
|gitea_additional_options|List of additional key=value for the Gitea quadlet container<br>ex: - "Network=custom.network"<br>Can also be used to leave comments by preceding with a '#'|list|False|[]|
|gitea_config_label|The labels for to the gitea config directory<br>Comma separated values (ex: rw,Z)|str|False||
|gitea_config_path|The path to the Gitea config directory.|str|False|~/.config/gitea/config/|
|gitea_data_label|The labels for to the gitea data directory<br>Comma separated values (ex: rw,Z)|str|False||
|gitea_data_path|The path to the Gitea data directory.|str|False|~/.local/share/containers/storage/gitea_data/|
|gitea_db_additional_options|List of additional key=value for the database quadlet container<br>ex: - "Network=custom.network"<br>Can also be used to leave comments by preceding with a '#'|list|False|[]|
|gitea_db_backend|The database backend to use.|str|False|psql|<ul><li>psql</li><li>mysql</li><li>sqlite</li></ul>
|gitea_db_label|The labels for to the database directory<br>Comma separated values (ex: rw,Z)|str|False||
|gitea_db_path|The path to the Gitea database directory.|str|False|~/.local/share/containers/storage/gitea_db/|
|gitea_ssh_port|The default port for the SSH server.|int|False|2222|
|gitea_version|The version of gitea Container|str|False|latest|<ul><li>latest</li><li>nightly</li></ul>
|gitea_web_port|The default port for the web server.|int|False|3000|


## Example Playbook

```
- hosts: all
  tasks:
    - name: Importing gitea role
      ansible.builtin.import_role:
        name: selfhosted.services.gitea
      vars:
```

## License

This project is licensed under the [MIT License](LICENSE)


⊂(▀¯▀⊂)

<!-- END_ANSIBLE_DOCS -->
