=================
ansible-role-zuul
=================

Ansible role to manage Zuul

* License: Apache License, Version 2.0
* Documentation: https://ansible-role-zuul.readthedocs.org
* Source: https://opendev.org/windmill/ansible-role-zuul
* Bugs: https://bugs.launchpad.net/ansible-role-zuul

Description
-----------

Zuul is a program that is used to gate the source code repository of a project
so that changes are only merged if they pass tests.

Requirements
------------

* pip3 to be installed if using zuul_install_method: (git|pip)

See `bindep.txt` for role dependencies.

Packages
~~~~~~~~

Package repository index files should be up to date before using this role, we
do not manage them.

SSH
~~~

An SSH private key will need to be installed before you can use zuul. The
contents of the private key will be used by ``zuul_config_gerrit_user`` and
should be copied to ``zuul_config_gerrit_sshkey``.

Role Variables
--------------

Zuul Merger Configuration
~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: yaml

    # Value to pass to git config user.email.
    # Default: Empty
    zuul_config_merger_git_user_email: ""

    # Value to pass to git config user.name.
    # Default: Empty
    zuul_config_merger_git_user_name: ""

Dependencies
------------

Example Playbook
----------------

.. code-block:: yaml

    - name: Install zuul
      hosts: zuul
      roles:
        - ansible-role-zuul
