# Pyenv setup with ansible

Ansible role to set up (pyenv)[https://github.com/pyenv/pyenv] and install different Python versions.

## Requirements

None.

## Role Variables

This is a sample variable structure used by this role:

    python_versions:
      - version: 3.7.7
      - version: 2.7.8
        state: absent
      - version: 3.8.3
        global: yes

### `python_versions.item.version`

The python version to install.

### `python_versions.item.state`

The state of installed Python version. Set `absent` to remove, `present` to install. Default: `present`. Optional

### `python_versions.item.global`

Set this python version as global. Only the last item set as `global` will be set as global Python version.

### `python_pyenv_dir`

Where to set up pyenv. Default: `~/.pyenv`

## Dependencies

None.

## Example Playbook

    - hosts: all
      vars:
        python_versions:
          - version: 3.7.7
          - version: 2.7.8
            state: absent
          - version: 3.8.3
            global: yes
        python_pyenv_dir: ~/.pyenv
      roles:
        - agoloncser.ansible-role-pyenv


## License

BSD

## Author Information

https://github.com/agoloncser
