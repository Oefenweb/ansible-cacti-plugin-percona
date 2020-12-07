## cacti-plugin-percona

[![Build Status](https://travis-ci.org/Oefenweb/ansible-cacti-plugin-percona.svg?branch=master)](https://travis-ci.org/Oefenweb/ansible-cacti-plugin-percona)
[![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-cacti--plugin--percona-blue.svg)](https://galaxy.ansible.com/Oefenweb/cacti-plugin-percona)

Set up [Percona MySQL Monitoring Template](https://www.percona.com/doc/percona-monitoring-plugins/1.0/cacti/mysql-templates.html) for Cacti in Debian-like systems.

#### Requirements

* `git` (will be installed)
* `perl-modules` (will be installed)
* `rsync` (will be installed)
* `php` (will **not** be installed)

#### Variables

* `cacti_plugin_percona_git_repo`: [default: `https://github.com/tersmitten/percona-monitoring-plugins.git`]: Percona MySQL Monitoring Template git repo (e.g. `https://github.com/percona/percona-monitoring-plugins.git`)
* `cacti_plugin_percona_version`: [default: `1.1.9`]: Only used in `{{ cacti_plugin_percona_git_version }}` (e.g. `1.1.8`)
* `cacti_plugin_percona_git_version`: [default: `"{{ cacti_plugin_percona_version }}"`]: What version of Percona MySQL Monitoring Template to check out (set up). This can be the full 40-character SHA-1 hash, the literal string HEAD, a branch name, or a tag name
* `cacti_plugin_percona_scripts_path`: [default: `/usr/share/cacti/site/scripts`]: Path of to `import_template.php`
* `cacti_plugin_percona_import_template_php_path`: [default: `/usr/share/cacti/cli/import_template.php`]:
* `cacti_plugin_percona_import_template_php_options`: [default: `[]`]: Options to pass to `import_template.php` (e.g. ['--remove-orphans'])
* `cacti_plugin_percona_ss_get_by_ssh_php_cnf`: [default: `[]`]: List of lines to be added to `"{{ cacti_plugin_percona_ss_get_by_ssh_php_cnf_file }}"`
* `cacti_plugin_percona_ss_get_mysql_stats_php_cnf`: [default: `[]`]: List of lines to be added to `"{{ cacti_plugin_percona_ss_get_mysql_stats_php_cnf_file }}"`
* `cacti_plugin_percona_ss_get_x_php_cnf_user`: [default: `root`]: Owner of the `.cnf` files
* `cacti_plugin_percona_ss_get_x_php_cnf_group`: [default: `www-data`]: Group of the `.cnf` files
* `cacti_plugin_percona_ss_get_x_php_cnf_mode`: [default: `0640`]: Mode of the `.cnf` files

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

##### Advanced

```yaml
---
- hosts: all
  roles:
    - cacti-plugin-percona
  vars:
    cacti_plugin_percona_scripts_path: /usr/share/cacti/site/scripts
    cacti_plugin_percona_import_template_php_path: /usr/share/cacti/cli/import_template.php
    cacti_plugin_percona_ss_get_by_ssh_php_cnf:
      - |
        $ssh_user = 'cacti_client';
        $ssh_iden = '-i /etc/cacti/id_rsa';

        $nc_cmd = 'nc -q1';
    cacti_plugin_percona_ss_get_mysql_stats_php_cnf:
      - |
        $mysql_user = 'cacti_client';
        $mysql_pass = 'secret';
        $mysql_port = 3306;
        $mysql_socket = NULL;
        $mysql_flags = MYSQLI_CLIENT_SSL | MYSQLI_CLIENT_SSL_DONT_VERIFY_SERVER_CERT;
        $mysql_ssl = true;
        $mysql_ssl_key  = '/etc/mysql/client-key.pem';
        $mysql_ssl_cert = '/etc/mysql/client-cert.pem';
        $mysql_ssl_ca = '/etc/mysql/ca-cert.pem';

        // $debug = true;
        // $debug_log = '/tmp/ss_get_mysql_stats.log';
```

#### License

MIT

#### Author Information

* Mischa ter Smitten

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Oefenweb/ansible-cacti-plugin-percona/issues)!
