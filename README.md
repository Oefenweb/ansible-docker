## docker

[![Build Status](https://travis-ci.org/Oefenweb/ansible-docker.svg?branch=master)](https://travis-ci.org/Oefenweb/ansible-docker) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-docker-blue.svg)](https://galaxy.ansible.com/list#/roles/2309)

Set up the latest version of [Docker Engine](https://docs.docker.com/engine/) in Ubuntu systems.

#### Requirements

None

#### Variables

* `docker_binary` [optional]: Customize location of Docker binary (especially for development testing) (e.g. `/usr/local/bin/docker`)
* `docker_opts` [optional]: Modify the daemon startup options (e.g. ['--dns 8.8.8.8', '--dns 8.8.4.4'])
* `docker_http_proxy` [optional]: If you need Docker to use an HTTP proxy, it can (also) be specified here (e.g. `http://127.0.0.1:3128/`)
* `docker_tmpdir` [optional]: This is also a handy place to tweak where Docker's temporary files go (e.g. `/mnt/bigdrive/docker-tmp`)

* `docker_manage_ufw` [default: `true`]: Whether or not `ufw` should be managed (change default forward policy) by this role
* `docker_manage_updatedb` [default: `true`]: Whether or not `updatedb` should be managed (disable indexing of `/var/lib/docker`) by this role

## Dependencies

None

## Recommended

* `ansible-updatedb` ([see](https://github.com/Oefenweb/ansible-updatedb), when `docker_manage_ufw` is `false`)
* `ansible-ufw` ([see](https://github.com/Oefenweb/ansible-ufw), when `docker_manage_updatedb` is `false`)

#### Example

```yaml
---
- hosts: all
  roles:
    - docker
```

#### License

Apache v2.0

#### Author Information

Mischa ter Smitten (based on work of [angstwad](https://github.com/angstwad))

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Oefenweb/ansible-docker/issues)!
