## cacti-plugin-percona 

[![Build Status](https://travis-ci.org/Oefenweb/ansible-cacti-plugin-percona.svg?branch=master)](https://travis-ci.org/Oefenweb/ansible-cacti-plugin-percona) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-cacti--plugin--percona-blue.svg)](https://galaxy.ansible.com/Oefenweb/cacti-plugin-percona/)

Set up [Percona Monitoring Plugins](https://www.percona.com/software/mysql-tools/percona-monitoring-plugins) for Cacti in Debian-like systems.

#### Requirements

None

#### Variables

* `cacti_plugin_percona_install`: [default: `[]`]: Additional packages to install

* `cacti_server_client_dbuser`: [default: `cacti`]: The database user to use to login on the cacti client
* `cacti_server_client_dbpass`: [default: ``]: The database password to use to login on the cacti client

## Dependencies

None

## Recommended

* `cacti-server` ([see](https://github.com/Oefenweb/ansible-cacti-server))

#### Example(s)

##### Simple

```yaml
---
- hosts: all
  roles:
    - cacti-plugin-percona
```

#### License

MIT

#### Author Information

* Mark van Driel
* Mischa ter Smitten

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Oefenweb/ansible-cacti-plugin-percona/issues)!
