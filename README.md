# ansible-role-symfony2

[![Build Status](https://travis-ci.org/ansible-roles/ansible-role-symfony2.svg?branch=master)](https://travis-ci.org/ansible-roles/ansible-role-symfony2)
[![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-igor__mukhin.symfony2-blue.svg?style=flat)](https://galaxy.ansible.com/list#/roles/3073)
[![Supported Platforms](http://img.shields.io/badge/platforms-ubuntu-orange.svg?style=flat)](#)
[![Ansible Version](http://img.shields.io/badge/ansible%20version-1.5.3+-lightgray.svg?style=flat)](#)

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

## Requirements

You need to install php and proper deploy client (git, hg, svn) before run this role. See [tests/playbook.yml](tests/playbook.yml) for example.

Its strongly recommended to install external `composer` role that installed globally, support automatic updates, github token configuration to go over github's API rate limit etc. My choice is [kosssi.composer](https://galaxy.ansible.com/list#/roles/1119) role. In this case you need to specify `symfony2_composer_path` with actual path to composer. Otherwise `composer.phar` will be installed in project root directory.

## Installation

```bash
ansible-galaxy install igor_mukhin.symfony2
```

## Usage

### Minimal example

```yml
- hosts: all
  vars:
    symfony2_name: project
    symfony2_repo: git@github.com:repo/project.git

  roles:
    - igor_mukhin.symfony2
```

Will install your application to /var/www/project/releases/20150114_074000/
(if you run that at 2015-01-14 7:40).

### Using role with Symfony 2.8+

To use role with Symfony 2.8+ we should specify valid 
path to `console`:

```yaml
symfony2_console_path: bin/console
```

## Warning

This role is under development right now. Some features not well tested, so may not work. Some minor releases may break BC until version 1 released.

Please, report your use case if you got problems with this role usage.

## Known issues

With `symfony2_ownership: none` (default value) there are not allowed to use `app/console` from bash as non-`symfony2_owner` user. Because it may generate cache with root owner and your apache will fail wo work with site. This probably ok on production where all console operations performs via cron with `www-data` (`symfony2_owner`) user.

You need to use `symfony2_ownership: chmod+a` or `symfony2_ownership: setfacl`.

## Contributing

Please, see [TODO.md](TODO.md) to get idea for contribution or implement your own things.

## License

MIT
