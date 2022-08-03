.. _user-roles:

=================================
User roles, types, and privileges
=================================

On this page you can find information about the different user roles and
privileges relevant to CrateDB Cloud. The first section describes these for the
users created within CrateDB Cloud: the organization and project roles,
respectively. The second section describes a different type of users, namely
CrateDB users, and their privileges and constraints.

In general, CrateDB Cloud users are created by the admins of their respective
organizations, and their function is to support project management for these
organizations in CrateDB Cloud. By contrast, CrateDB users are either generated
automatically or created as part of the CrateDB Cloud cluster deployment
process, and support the operation of CrateDB Cloud clusters specifically.

.. rubric:: Table of contents

.. contents::
   :local:


.. _user-roles-cloud:

CrateDB Cloud user roles
========================

This section describes the roles that can be set for users within CrateDB
Cloud. For information on how to do so, see our documentation on :ref:`adding
users <crate-reference:administration_user_management>`.


.. _org-roles:

Organization roles
------------------

An *organization admin* can add users to and remove users from an organization.
Admins can perform all available operations for projects and services. They
have access to the organization's Audit Log.

Each organization must have at least one admin.

An *organization member* is able to view the list of organization users but
can't edit, add, or remove users.

They only have access to projects they are part of.


.. _project-roles:

Project roles
-------------

A *project admin* can add users to and remove users from a project. They can
also perform every available operation inside that project.

.. NOTE::

    This means that an *organization member* who is also a *project admin* can
    perform all available operations within that project, but not within the
    organization.

A *project member* has read-only access to the project.


.. _user-roles-db:

CrateDB user roles
==================

This section covers users and privileges that derive from the architecture of
CrateDB as it operates for CrateDB Cloud. There are different types of CrateDB
database users that are relevant for CrateDB Cloud customers, and their nature
and constraints are described below.


.. _system-user:

``System`` user
---------------

In CrateDB Cloud, the backend uses a user called ``system`` in order to perform
Cloud cluster upgrades, backups and scaling functions, among other things.

.. WARNING::

    The user ``system`` is essential for CrateDB Cloud to function as intended.
    While it is not normally accessible through the CrateDB Cloud Console or
    the Croud CLI, it can be accessed through the CrateDB admin UI or any other
    SQL client. It is important not to edit or delete this user in any way.
    Otherwise, the functioning of Cloud clusters may be compromised.


.. _crate-user:

``Crate`` user
--------------

In CrateDB, when you create a cluster node (through whatever method), a
``crate`` user is automatically generated. ``crate`` is a superuser and can
perform all possible operations. It is not possible to create additional
superusers.


.. _db-user:

Regular database user
---------------------

Next to the ``crate`` user there is the regular database user, created as part
of the CrateDB Cloud cluster deployment wizard when deploying a cluster through
:ref:`AWS <cloud-tutorials:signup-aws-to-cluster>` or
:ref:`Azure <cloud-tutorials:signup-azure-to-cluster>`.

Because the regular database user has `AL privileges`_, there are certain
operations that they cannot perform. As of CrateDB 4.2.1, the list of such
operations is as follows:

| ``ALTER CLUSTER``
| ``ANALYZE``
| ``DISCARD``
| ``KILL``
| ``KILL ALL``
| ``OPTIMIZE``
| ``SET LICENSE``
| ``SET TRANSACTION``

More information on CrateDB user privileges can be found in the :ref:`CrateDB
documentation on privileges <crate-reference:administration-privileges>`.


.. _AL privileges: https://crate.io/docs/crate/reference/en/latest/admin/privileges.html#al
