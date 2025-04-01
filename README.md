# ansible-role-act_runner

Deployment and configuration of [nektos act](https://github.com/nektos/act) runners, typically for [Gitea](https://gitea.com).

# Requirements
## Windows
- Ansible collection: `community.windows`
- [Chocolatey](https://chocolatey.org)

# Usage

Add the role to your `requirements.yml`:

```yml
roles:
  - name: frozenfoxx.act_runner
```

Invoke the role:

```yml
---
- name: Act runners (Debian)
  hosts: debian
  tasks:
    - name: Install Act runner
      ansible.builtin.import_role:
        name: frozenfoxx.act_runner

- name: Act runners (Windows)
  hosts: windows
  tasks:
    - name: Install Act runner
      ansible.builtin.import_role:
        name: frozenfoxx.act_runner
      vars:
        act_runner_location: "C:\act_runner"
        act_runner_labels: ["windows:host"]
```

# Contribution

Pull requests welcome.