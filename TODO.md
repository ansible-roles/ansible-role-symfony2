# TODO

Releases:
[ ] Automatically getting previous release
[ ] Check current release greather than previous
[ ] Copy hard linked previous release files to speed up deploy
[ ] Remove failed releases before remove old releases (check some deploy.lock file existence that created on start and deleted on successfull deploy)

Rights:
[x] Different rights strategies (chmod+a, setfacl, chmod)
[x] User/Group defaults

Tests:
[x] Test playbook
[x] Vagrantfile
[x] Travis
[ ] Travis badge

Examples:
[ ] Multiple sites per one playbook example
[ ] kosssi.composer when a lot of libraries used to prevent github limit
[ ] github.com at .known_hosts

Etc:
[x] Pre-deploy checks
[ ] Maintenance mode
