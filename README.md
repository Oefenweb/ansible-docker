## docker

[![CI](https://github.com/Oefenweb/ansible-docker/workflows/CI/badge.svg)](https://github.com/Oefenweb/ansible-docker/actions?query=workflow%3ACI)
[![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-docker-blue.svg)](https://galaxy.ansible.com/Oefenweb/docker)

Set up the latest version of [Docker Engine](https://docs.docker.com/engine/) in Debian-like systems.

#### Requirements

* `apt-transport-https` (will be installed)
* `ca-certificates` (will be installed)
* `curl` (will be installed)
* `software-properties-common` (will be installed)
* `apparmor` (will be installed)
* `linux-image-extra-virtual` (will be installed, Ubuntu only)
* `cgroup-lite` (will be installed, Ubuntu only)

#### Variables

* `docker_etc_default_binary` [optional]: Customize location of Docker binary (especially for development testing) (e.g. `/usr/local/bin/docker`)
* `docker_etc_default_opts` [optional]: Modify the daemon startup options (e.g. `['--dns 8.8.8.8', '--dns 8.8.4.4']`)
* `docker_etc_default_http_proxy` [optional]: If you need Docker to use an HTTP proxy, it can (also) be specified here (e.g. `http://127.0.0.1:3128/`)
* `docker_etc_default_tmpdir` [optional]: This is also a handy place to tweak where Docker's temporary files go (e.g. `/mnt/bigdrive/docker-tmp`)

* `docker_manage_ufw` [default: `true`]: Whether or not `ufw` should be managed (change default `FORWARD` policy) by this role
* `docker_manage_updatedb` [default: `true`]: Whether or not `updatedb` should be managed (disable indexing of `/var/lib/docker`) by this role

## Dependencies

None

## Recommended

* `ansible-updatedb` ([see](https://github.com/Oefenweb/ansible-updatedb), when `docker_manage_ufw` is `false`)
* `ansible-ufw` ([see](https://github.com/Oefenweb/ansible-ufw), when `docker_manage_updatedb` is `false`)

* `ansible-docker-compose` ([see](https://github.com/Oefenweb/ansible-docker-compose))
* `ansible-docker-machine` ([see](https://github.com/Oefenweb/ansible-docker-machine))

#### Example

```yaml
---
- hosts: all
  roles:
    - oefenweb.docker
```

#### License

Apache v2.0

#### Author Information

Mischa ter Smitten (based on work of [angstwad](https://github.com/angstwad))

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Oefenweb/ansible-docker/issues)!
