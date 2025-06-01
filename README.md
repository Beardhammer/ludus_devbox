# Ansible Role: Rustdesk Server/Client Installs

An Ansible Role that preps a Windows Server for developing payloads in docker

## Requirements

None.

## Role Variables
None.

## Dependencies

None.

## Installing
ludus ansible role add Beardhammer.ludus_devbox

## Example Ludus Range Config

```yaml
ludus:
  - vm_name: "Win2022-Server"
    hostname: "Win2022-Server"
    template: win2022-server-x64-template
    vlan: 10
    ip_last_octet: 22
    ram_gb: 8
    cpus: 4
    windows:
      sysprep: true
    roles:
      - name: devbox-windows
      - name: Beardhammer.ludus_rustdesk
        depends_on:
          - vm_name: PL-rustdesk
            role: Beardhammer.ludus_rustdesk
    role_vars:
      rustdesk_client: true

```

## License

GPLv3

## Author Information

This role was created by [beardhammer](https://github.com/Beardhammer), for [Ludus](https://ludus.cloud/).
