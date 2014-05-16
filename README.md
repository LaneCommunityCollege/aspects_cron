cron
========

Manage anacrontab, crontab, and normal user cronjobs with simple dictionary definitions.

Requirements
------------
Set ```hash_behaviour=merge``` in your ansible.cfg file.

Assumes anacron is installed. If it isn't installed, you just end up with an unused /etc/anacrontab file.

Role Variables
--------------

Variables should be self explanatory. If any are confusing, checking the anacrontab or crontab man pages should clear things up. 

License
-------

MIT
