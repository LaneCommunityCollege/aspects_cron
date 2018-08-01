cron
========

Manage anacrontab, crontab, and normal user cronjobs with simple dictionary definitions.

Requirements
------------
Set ```hash_behaviour=merge``` in your ansible.cfg file.

Role Variables
--------------

Variables should be self explanatory. If any are confusing, checking the anacrontab or crontab man pages should clear things up.

### aspects_cron_enabled
If False, do not run tasks in this role.

If True, run tasks in this role.

# Dependencies
## aspects_packages
[aspects_packages](https://github.com/LaneCommunityCollege/aspects_packages) is used to install `cronie-anacron` on OracleLinux 6. The Vagrant box I used while testing did not have any crontab utility installed. 

If you don't want to use `aspects_packages`, just set `aspects_packages_enabled: False`.

License
-------

MIT
