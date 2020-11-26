## cacti-plugin-percona

[![Build Status](https://travis-ci.org/Oefenweb/ansible-cacti-plugin-percona.svg?branch=master)](https://travis-ci.org/Oefenweb/ansible-cacti-plugin-percona)
[![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-cacti--plugin--percona-blue.svg)](https://galaxy.ansible.com/Oefenweb/cacti-plugin-percona)

Set up [Percona MySQL Monitoring Template](https://www.percona.com/doc/percona-monitoring-plugins/1.0/cacti/mysql-templates.html) for Cacti in Debian-like systems.

#### Requirements

None

#### Variables

* `cacti_plugin_percona_install`: [default: `[]`]: Additional packages to install

## Dependencies

None

## Recommended

* `cacti-client` ([see](https://github.com/Oefenweb/ansible-cacti-client))
* `cacti-server` ([see](https://github.com/Oefenweb/ansible-cacti-server))
* `cacti-spine` ([see](https://github.com/Oefenweb/ansible-cacti-spine))

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

* Mischa ter Smitten

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Oefenweb/ansible-cacti-plugin-percona/issues)!
