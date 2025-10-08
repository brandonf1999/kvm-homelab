# kvm_libvirt (Rocky 10)

A tiny, pragmatic role to get KVM/QEMU and libvirt ready on Rocky Linux 10.


## Variables
See `defaults/main.yml` for all options. Common ones:


- `kvm_libvirt_users`: list of users to add to `libvirt` group.
- `kvm_libvirt_enable_nested`: set to `true` to enable nested virtualization.
- `kvm_libvirt_ensure_default_network`: ensure the `default` NAT network is active and autostarts.


## Example playbook
```yaml
- hosts: kvm_hosts
  become: true
  roles:
    - role: kvm_libvirt
      vars:
        kvm_libvirt_users: ["admin"]
        kvm_libvirt_enable_nested: true
        kvm_libvirt_ensure_default_network: true
        kvm_libvirt_manage_firewall: false
```
