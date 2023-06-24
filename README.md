# Overview

This role upgrades the linux systems and performs the actions needed to apply the upgrade is needed:
- reboot
- restart services

You can specify a verification command that will validate the system is healthy after upgrade.

This role requires root permissions. It must be called as root. This needs to be managed at the ansible or playbook level.

# Variables

| Name  | Type | Required | Default Value | Description |
| ----- | ---- | -------- | ------------- | ----------- |
| system_upgrade_pre_reboot_delay | integer | no | n.a. | How long in seconds to wait before rebooting the system |
| system_upgrade_post_reboot_delay | integer | no | n.a. | How long in seconds to wait after rebooting the system to check the health |
| system_upgrade_reboot_timeout | integer | no | n.a. | How long in seconds to wait after rebooting the system before considering it failed if not responding |
| system_upgrade_test_command | string | no | n.a. | Absolute path of a script validating the health of the system. Return 0 for healthy |


# Automatique Testing

This role is tested using Molecule against:
- Python 3.9 and 3.10
- CentOS 7/8
- RockyLinux 9
- Debian 9/10/11/12
