# Proviso
[![Build
Status](https://travis-ci.org/proviso/proviso.png)](https://travis-ci.org/proviso/proviso)

Proviso aims to be an SDK+API to provision platform-independent local
VMs for Drupal development. The project seeks to develop an extensible
framework and ecosystem for developers to achieve parity with multiple
production deployment targets, as well as a one-click installer control
panel that makes advanced local development accessible.

For full documentation information, please see the
[Wiki](https://github.com/proviso/proviso/wiki).

To participate, see [contributing](https://github.com/proviso/proviso/blob/master/CONTRIBUTING.md).

Features
--------

- `vagrant-vbguest`: Ensures that [Virtualbox Guest
Additions][vbox-guest-additions] are up-to-date, for stable
virtualization behavior.
- [`vagrant-cachier`][vagrant-cachier]: Caches APT system packages
between VM destroys, for faster builds.

Usage
-----

### 1. Setup

    git clone https://github.com/proviso/proviso.git && cd proviso
    rake install_plugins

### 2a. Chef

    vagrant up

### 2b. Puppet

    [sudo] gem install librarian-puppet
    cd puppet && librarian-puppet install
    PROVISO_PROVISIONER=puppet vagrant up

When using Puppet, you'll need to preface every vagrant command with
`PROVISO_PROVISIONER=puppet`. To avoid having to type this for each
command, you may also export this environment variable for the remainder
of your terminal session by running:

    export PROVISO_PROVISIONER=puppet

<!-- Links -->
   [vbox-guest-additions]: http://www.virtualbox.org/manual/ch04.html
   [vagrant-cachier]: https://github.com/fgrehm/vagrant-cachier#readme
