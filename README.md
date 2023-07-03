
[![Build Status](https://travis-ci.org/rezizter/ansible_prom2teams.png)](https://app.travis-ci.com/github/rezizter/ansible_prom2teams)

# prom2teams Ansible role for EL7

This Ansible role installs prom2teams in a CentOS 7 environment.

- [Getting Started](#getting-started)
	- [Prerequisities](#prerequisities)
	- [Installing](#installing)
- [Usage](#usage)
- [Testing](#testing)
- [Built With](#built-with)
- [Versioning](#versioning)
- [Authors](#authors)
- [License](#license)
- [Contributing](#contributing)

## Credit

This is based on a similar role for Debian by *idealista* on this project: https://github.com/idealista/prom2teams_role
I modified this role for CentOS 7.

## Getting Started

These instructions will get you a copy of the role for your ansible playbook. Once launched, it will install a [prom2teams](https://github.com/idealista/prom2teams) server on a CentOS 7 server.

### Prerequisities

Ansible >=2.9 version installed.

For testing purposes, [Molecule](https://molecule.readthedocs.io/) with [Docker](https://www.docker.com/) as driver. Pipenv >=2018.11.26 and Python 3.6 recommended.

### Installing

Create or add to your roles dependency file (e.g requirements.yml) from GitHub:

```
- src: https://github.com/rezizter/ansible_prom2teams.git
  scm: git
  version: 1.0.0
  name: ansible_prom2teams
```

or using [Ansible Galaxy](https://galaxy.ansible.com/rezizter/ansible_prom2teams/) as origin if you prefer:

```
- src: rezizter.ansible_prom2teams
  version: master
  name: rezizter.ansible_prom2teams
```

Install the role with ansible-galaxy command:

```
ansible-galaxy install -p roles -r requirements.yml -f
```

Use in a playbook:

```
---
- hosts: someserver
  roles:
    - rezizter.ansible_prom2teams
```

## Usage

Look to the [defaults](defaults/main.yml) properties file to see the possible configuration properties.

Mandatory property is `prom2teams_webhook_urls`. For example:

```
prom2teams_webhook_urls:
  connector1: http://test
  connector2: http://test2
```

## Testing

```
pipenv shell
pipenv sync
molecule test
```

See `molecule.yml` to check possible testing platforms.

## Built With

![Ansible](https://img.shields.io/badge/ansible-2.14.2-green.svg)

## Versioning

For the versions available, see the [tags on this repository](https://github.com/rezizter/ansible_prom2teams/tags).

Additionaly you can see what change in each version in the [CHANGELOG.md](CHANGELOG.md) file.

## License

![GNU General Public License v3.0](https://img.shields.io/badge/License-GNU%20GPL-blue)

## Contributing

Please read [CONTRIBUTING.md](.github/CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.
