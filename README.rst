superlance README
=================

Superlance is a package of plugin utilities for monitoring and controlling
processes that run under `supervisor <http://supervisord.org>`_.

Please see ``docs/index.rst`` for complete documentation.

`superlance Docs <https://superlance.readthedocs.io/en/latest/index.html>`_.

change
==========

httpok
======
added new feature:

1. can config supervisor with username and password.

2. can send alert message to dingding.

supervisor eventlistener example:

[eventlistener:cat]

command=httpok -p myServiceName -t 15 -s "mail -s [Supervisor]Service State Changed admin@example.com" -m "admin@example.com" -u supervisorUser -P "SupervisorPWD" -D -T 21xxxxxxxxx0d4d http://localhost:8080/monitor

events=TICK_60

stdout_logfile=/tmp/stdout.log

stderr_logfile=/tmp/stderr.log

stdout_logfile_maxbytes=10MB

stdout_logfile_backups=1

redirect_stderr=false

autostart=true

autorestart=true

httpok new args
===============
using httpok --help

-u --username=: supervisor username.

-P --password=: supervisor password.

-D --dingding: is send alert message to dingding.

-T --token=: dingding token.
