Getting started
===============

.. include:: includes/all.rst

.. contents::
   :local:


Example inventory
-----------------

Add the linuxmuster.net client which should be configured to the
``ypid_service_linuxmuster_net_client`` Ansible inventory host group:

.. code:: ini

   [ypid_service_linuxmuster_net_client]
   hostname

Example playbook
----------------

Here's an example playbook that uses the ``ypid.linuxmuster_net_client`` role:

.. literalinclude:: playbooks/linuxmuster_net_client.yml
   :language: yaml

The playbooks is shipped with this role under
:file:`docs/playbooks/linuxmuster_net_client.yml` from which you can symlink it to your
playbook directory.
In case you use multiple roles maintained by ypid_, consider
using the `ypid-ansible-common`_.

Ansible tags
------------

You can use Ansible ``--tags`` or ``--skip-tags`` parameters to limit what
tasks are performed during Ansible run. This can be used after a host was first
configured to speed up playbook execution, when you are sure that most of the
configuration is already in the desired state.

Available role tags:

``role::linuxmuster_net_client``
  Main role tag, should be used in the playbook to execute all of the role
  tasks as well as role dependencies.

``role::linuxmuster_net_client:pkgs``
  Tasks related to system package management like installing or
  removing packages.
