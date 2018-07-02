Ansible Role: chrome [![Build Status](https://travis-ci.com/dswhitley/ansible-role-chrome.svg?branch=master)](https://travis-ci.com/dswhitley/ansible-role-chrome)
=====================================

This role will install the [Chrome](https://www.google.com/chrome/) browser.

The repository varies between OSes and even between versions of the same OS.
But in the end, it is widely available in repositories so this is how it is
installed for the various OSes supported in this role.

Important Notes
---------------

* This role will install the latest version of the package and therefore uses
  the "latest" state which is largely frowned upon
* There are some site specific configurations for the browser, but this role
  will simply install the package.  Any subsequent configuration will be
  handled in a different, site-specific role

Requirements
------------

Any package or additional repository requirements will be addressed in the role.

Role Variables
--------------

N/A

Example Playbook
----------------

Here is an example playbook:

```yaml
- hosts: localhost
  connection: local
  roles:
    - role: chrome
```

Inclusion
---------

I envision this role being included in a larger project through the use of a
`requirements.yml` file.  So here is an example of what you would need in your
file:

```yaml
# get the chrome role from github
- src: https://github.com/dswhitley/ansible-role-chrome.git
  scm: git
  name: chrome
```

Have the above in a `requirements.yml` file for your project would then allow
you to "install" it (prior to use in some sort of setup script?) with:

```bash
ansible-galaxy install -p ./roles -r requirements.yml
```

Testing
-------

I am relying heavily on the work by Jeff Geerling in using Travis CI for testing
this role.  Here is a list of OSes currently being tested (using geerlingguy's
container images):

* centos7
* centos6
* fedora27
* ubuntu1804
* ubuntu1604
* ubuntu1404
* debian9
* debian8

To-do
-----

N/A

References
----------

* [How I test Ansible configuration on 7 different OSes with Docker](https://www.jeffgeerling.com/blog/2018/how-i-test-ansible-configuration-on-7-different-oses-docker)

License
-------

All parts of this project are made available under the terms of the [MIT
License](LICENSE).
