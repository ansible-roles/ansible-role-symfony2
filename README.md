ansible-role-symfony2
=====================

Ansible role to deploy Symfony2 application.

It can deploy via `rsync`, `git`, `svn` and `mercurial`, generate `parameters.yml` if needed, run `php app/console` commands you defined.

It make capifony-like directory structure:

```bash
  root
    releases
      release
    shared
      web/uploads
      app/config
      app/logs
    current
```

Requirements
------------

You need to install git, php, composer before run this role.

Installation
------------

```bash
ansible-galaxy install igor_mukhin.symfony2
```

Usage
-----

```yml
- hosts: all
  vars:
    symfony2_release: 1
    symfony2_name: project
    symfony2_domain: "project.com"
    symfony2_repo: git@github.com:repo/project.git

  roles:
    - igor_mukhin.symfony2
```

Warning
-------

This role is under development right now. Some features not well tested, so may not work. Some minor releases may break BC until version 1 released.

Please, report your use case if you got problems with this role usage.

License
-------

MIT
