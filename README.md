# aspects_cron

Manage anacrontab, crontab, and normal user cronjobs with simple dictionary definitions.

# Requirements

Set ```hash_behaviour=merge``` in your ansible.cfg file.

# Role Variables


Variables should be self explanatory. If any are confusing, checking the anacrontab or crontab man pages should clear things up.

### aspects_cron_enabled
If False, do not run tasks in this role.

If True, run tasks in this role.

# Dependencies
## aspects_packages
[aspects_packages](https://github.com/LaneCommunityCollege/aspects_packages) is used to install `cronie-anacron` on OracleLinux 6. The Vagrant box I used while testing did not have any crontab utility installed. 

If you don't want to use `aspects_packages`, just set `aspects_packages_enabled: False`.

# Example Playbook

```yaml
- hosts:
  - aspects_cron
  vars:
    aspects_cron_enabled: True
    aspects_packages_enabled: True
    aspects_cron_jobs:
      testecho:
        name: "Test echo job."
        state: "absent"
        backup: "no"
        minute: "23"
        hour: "3"
        day: "5"
        weekday: "5"
        month: "2"
        user: "root"
        job: "echo noghlsdkjf > /dev/null"
      testecho2:
        name: "Another Test echo job."
        state: "present"
        backup: "no"
        minute: "23"
        hour: "3"
        day: "5"
        weekday: "5"
        month: "2"
        user: "root"
        job: "echo noghlsdkjf > /dev/null"
  roles:
  - aspects_cron
```

# License

MIT
