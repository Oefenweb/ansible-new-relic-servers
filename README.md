## new-relic-servers

[![Build Status](https://travis-ci.org/Oefenweb/ansible-new-relic-servers.svg?branch=master)](https://travis-ci.org/Oefenweb/ansible-new-relic-servers) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-new--relic--servers-blue.svg)](https://galaxy.ansible.com/Oefenweb/ansible-new-relic-servers)

Set up [New Relic Servers](https://newrelic.com/server-monitoring) in Debian-like systems.

#### Requirements

None

#### Variables

* `new_relic_servers_license_key`: [required]: License key. 40-character hexadecimal string provided by New Relic. This is required in order for the server monitor to start
* `new_relic_servers_loglevel`: [optional, default `info`]: Level of detail you want in the log file
* `new_relic_servers_logfile`: [optional, default `/var/log/newrelic/nrsysmond.log`]: Name of the file where the server monitor will store it's log message
* `new_relic_servers_ssl`: [optional, default `true`]: If you prefer the daemon to use the secure HTTP (https) protocol when communicating with the New Relic collector servers
* `new_relic_servers_hostname`: [optional, default `inventory_hostname`]: Sets the name of the host (max 64 characters) that you wish to use for reporting
* `new_relic_servers_pidfile`: [optional, default `/var/run/newrelic/nrsysmond.pid`]: Name of a file where the server monitoring daemon will store it's process ID (PID)
* `new_relic_servers_disable_nfs`: [optional, default `false`]: Set to true to disable NFS client statistics gathering
* `new_relic_servers_disable_docker`: [optional, default `false`]: Set to true to disable Docker container statistics gathering
* `new_relic_servers_ignore_reclaimable`: [optional, default `true`]: Set to true if the memory the kernel refers to as "reclaimable slabs" should be ignored when calculating how much RAM is in use

## Dependencies

None

#### Example(s)

##### Simple

```yaml
---
- hosts: all
  roles:
    - new-relic-servers
  vars:
    new_relic_servers_license_key: da39a3ee5e6b4b0d3255bfef95601890afd80709
```

#### License

MIT

#### Author Information

* Mischa ter Smitten

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Oefenweb/ansible-new-relic-servers/issues)!
