# Changelog

## 0.4.*

* Added: `symfony2_repo_depth` variable to control `depth` during git pull
* Optimized: By default git pull with `depth=1` now
* Added: Ability to provide `key_file` for git
* Reworked: Now `symfony2_composer_path` always defined and have '' as default

## 0.3.*

* Hard-coded `www-data` now replaced with `{{ symfony2_owner }}` and `{{ symfony2_group }}`.
* Also, `{{ symfony2_owner }}` is equal to `{{ ansible_ssh_user }}` now by default.
