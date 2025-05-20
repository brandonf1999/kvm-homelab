# 🖥️ Ansible Role: `kvm_libvirt`

This Ansible role installs and configures a basic virtualization layer using **KVM** and **libvirt** on Linux hosts. It supports both **Debian/Ubuntu** and **RHEL/CentOS** systems.

---

## ✅ Features

- Installs KVM, libvirt, and related virtualization tools
- Enables and starts `libvirtd` service
- Optional: Enables **nested virtualization** for Intel/AMD CPUs
- Installs additional KVM packages if specified
- Automatically detects supported Linux distribution

---

## 📦 Role Variables

| Variable                     | Default  | Description                                                  |
|-----------------------------|----------|--------------------------------------------------------------|
| `enable_nested_virtualization` | `true`   | Enables nested virtualization if supported                   |
| `extra_kvm_packages`        | `[]`     | Optional list of extra packages to install (e.g. `virt-top`) |

You can override these variables in your playbook or inventory.

---

## 🧩 Dependencies

None

---

## 🚀 Example Playbook

```yaml
- name: Provision a KVM virtualization host
  hosts: kvm_hosts
  become: true
  roles:
    - role: kvm_libvirt
      vars:
        enable_nested_virtualization: true
        extra_kvm_packages:
          - virt-top

