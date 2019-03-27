Allow root ssh login into cloud boxes
=====================================

Most of the default distro images disallow root ssh connections, as a potential
security measure.  This Ansible role reverts back the changes in cloud-init
configuration, same as the changes in root's authorized\_keys file.

Btw, if you hate the error messages:

    Please login as the user "centos" rather than the user "root".
    Please login as the user "fedora" rather than the user "root"
    Please login as the user "cloud-user" rather than the user "root".

Then you'll probably love this role.

Howto
-----

Basic wrapper playbook (default `remote_user == 'root'`):

```yaml
- hosts: all
  gather_facts: False
  roles:
  - role: ansible-fix-ssh-root

```

Have a look at `./example` directory.
