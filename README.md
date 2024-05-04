# .sysops

Configuration management using [Ansible](https://docs.ansible.com/) for my
systems.

## Requirements

Per host requirements:

### Windows

- Ensure
  [a WinRM listener is set up](https://docs.ansible.com/ansible/latest/os_guide/windows_setup.html#setup-winrm-listener)
  and the service is running/enabled at startup.
- Install the `pywinrm` and `requests-ntlm` python packages

> 💡 `ansible --ask-pass -i windows.ini windows -m win_ping` can be used to ping
> the Windows host to check if installation is successful.

## Usage

Roles source variables using the OS name.

To run configuration setup for Arch Linux desktop (locally), run:
`ansible-playbook --ask-become archlinux_desktop.yml`

To run a plays against Windows host run:
`ansible-playbook --ask-pass windows_desktop.yml -i windows.ini`
