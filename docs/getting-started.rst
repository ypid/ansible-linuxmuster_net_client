Getting started
===============

.. contents::
   :local:

.. include:: includes/all.rst


Example inventory
-----------------

Add the linuxmuster.net client which should be configured to the
``ypid_service_linuxmuster_net_client`` Ansible inventory host group:

.. code:: ini

   [ypid_service_linuxmuster_net_client]
   hostname

Example playbook
----------------

Here's an example playbook that can be used to configure a linuxmuster.net
client:

.. literalinclude:: playbooks/linuxmuster_net_client.yml
   :language: yaml

Ansible tags
------------

You can use Ansible ``--tags`` or ``--skip-tags`` parameters to limit what
tasks are performed during Ansible run. This can be used after host is first
configured to speed up playbook execution, when you are sure that most of the
configuration has not been changed.

Available role tags:

``role::linuxmuster_net_client``
  Main role tag, should be used in the playbook to execute all of the role
  tasks as well as role dependencies.
