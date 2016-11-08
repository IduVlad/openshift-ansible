[![Join the chat at https://gitter.im/openshift/openshift-ansible](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/openshift/openshift-ansible)

# OpenShift Ansible

This repository contains [Ansible](https://www.ansible.com/) code to install,
upgrade and manage [OpenShift](https://www.openshift.com/) clusters.

**Note**: the Ansible playbooks in this repository require an RPM package that
provides `docker`. Currently, the RPMs from
[dockerproject.org](https://dockerproject.org/) do not provide this requirement,
though they may in the future. This limitation is being tracked by
[#2720](https://github.com/openshift/openshift-ansible/issues/2720).

## Branches and tags

The [master branch](https://github.com/openshift/openshift-ansible/tree/master)
tracks our current work and should be compatible with both [Origin master
branch](https://github.com/openshift/origin/tree/master) and the [most recent
Origin stable release](https://github.com/openshift/origin/releases). Currently
that's v1.4 and v1.3.x. In addition to the master branch, we maintain stable
branches corresponding to upstream Origin releases, e.g.:
[release-1.2](https://github.com/openshift/openshift-ansible/tree/release-1.2).
The most recent branch will often receive minor feature backports and fixes.
Older branches will receive only critical fixes.

Releases are tagged periodically from active branches and are versioned 3.x
corresponding to Origin releases 1.x. We unfortunately started with 3.0 and it's
not practical to start over at 1.0.

## Setup

- Install base dependencies:
  - Requirements:
    - Ansible >= 2.1.0 though 2.2 is preferred for performance reasons.
    - Jinja >= 2.7

  - Fedora:
    ```
    dnf install -y ansible-2.1.0.0 pyOpenSSL python-cryptography
    ```

- Setup for a specific cloud:
  - [AWS](http://github.com/openshift/openshift-ansible/blob/master/README_AWS.md)
  - [GCE](http://github.com/openshift/openshift-ansible/blob/master/README_GCE.md)
  - [local VMs](http://github.com/openshift/openshift-ansible/blob/master/README_libvirt.md)

- Bring your own host deployments:
  - [OpenShift Enterprise](https://docs.openshift.com/enterprise/latest/install_config/install/advanced_install.html)
  - [OpenShift Origin](https://docs.openshift.org/latest/install_config/install/advanced_install.html)
  - [Atomic Enterprise](http://github.com/openshift/openshift-ansible/blob/master/README_AEP.md)

- Build
  - [How to build the openshift-ansible rpms](BUILD.md)

- Directory Structure:
  - [bin/cluster](https://github.com/openshift/openshift-ansible/tree/master/bin/cluster) - python script to easily create clusters
  - [docs](https://github.com/openshift/openshift-ansible/tree/master/docs) - Documentation for the project
  - [filter_plugins/](https://github.com/openshift/openshift-ansible/tree/master/filter_plugins) - custom filters used to manipulate data in Ansible
  - [inventory/](https://github.com/openshift/openshift-ansible/tree/master/inventory) - houses Ansible dynamic inventory scripts
  - [playbooks/](https://github.com/openshift/openshift-ansible/tree/master/playbooks) - houses host-type Ansible playbooks (launch, config, destroy, vars)
  - [roles/](https://github.com/openshift/openshift-ansible/tree/master/roles) - shareable Ansible tasks

## Contributing

- [Best Practices Guide](https://github.com/openshift/openshift-ansible/blob/master/docs/best_practices_guide.adoc)
- [Core Concepts](https://github.com/openshift/openshift-ansible/blob/master/docs/core_concepts_guide.adoc)
- [Style Guide](https://github.com/openshift/openshift-ansible/blob/master/docs/style_guide.adoc)
