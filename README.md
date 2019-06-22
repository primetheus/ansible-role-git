# Ansible Role: Git

Installs and configures Git from source on RHEL/CentOS or Debian/Ubuntu servers. This role is not intended to make use of package repositories, such as YUM, DNF, Apt or any others... it is intentionally installing from source.

## Requirements

No special requirements; note that this role requires root access, so either run it in a playbook with a global `become: yes`, or invoke the role in your playbook like:

    - hosts: devopsbox
      roles:
        - role: primetheus.git
          become: yes

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
git_version: latest
```
The version of `git` to install
```yaml
git_source_url: "https://api.github.com/repos/git/git/tarball/v{{ git_version }}"
```
The URL to pull the source from. This can also pull from `https://mirrors.edge.kernel.org/pub/software/scm/git/git-{{ git_version }}.tar.gz` if you find that to be more suitable.
```yaml
git_install_dir: /usr/local/git
```
Where to install the package

## Dependencies

None.

## Example Playbook
```yaml
- hosts: devopsbox
  become: yes
  roles:
    - primetheus.git
```

## License

MIT / BSD

## Author Information

This role was created in 2018 by Jared Murrell.
