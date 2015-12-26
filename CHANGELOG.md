# Changelog

## 0.6.0

* Now you can specify you own list of
  shared directories at `symfony2_shared_dirs`
* Data from `symfony2_shared_dirs` will be moved
  to shared dir from release dir during first run
* Added `symfony2_php_args` parameter with default value `-d memory_limit=-1`
  to prevent not enough `memory_limit` composer fails
* Improved comments at defaults/main.yml
* Small fixes at README.md

## 0.5.*

* Fixed `symfony2_release_regexp` format
* Only those releases will be removed who match `symfony2_release_regexp`
* `symfony2_release` generates now if it empty

## 0.4.*

* Added: `symfony2_repo_depth` variable to control `depth` during git pull
* Optimized: By default git pull with `depth=1` now
* Added: Ability to provide `key_file` for git
* Reworked: Now `symfony2_composer_path` always defined and have '' as default

## 0.3.*

* Hard-coded `www-data` now replaced with `{{ symfony2_owner }}` and `{{ symfony2_group }}`.
* Also, `{{ symfony2_owner }}` is equal to `{{ ansible_ssh_user }}` now by default.
