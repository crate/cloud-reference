.. _concepts:

========
Concepts
========

The purpose of this article is to provide information on the main concepts
encountered while working with, or reading the Documentation of, CrateDB Cloud.
By providing a brief explanation of these concepts, we hope to make the
structure of CrateDB Cloud easier to understand. The concepts discussed here
are the three primary components of the Cloud structure: organizations,
projects, and services.

This is not a full glossary. We intend to provide a more complete glossary in
the future.

.. rubric:: Table of contents

.. contents::
   :local:


.. _concepts-orgs:

Organizations
=============

*Organizations* represent the larger structure - for example a company - within
which CrateDB Cloud projects and associated services are deployed. At the
organization level there is always at least one organization administrator, who
can in turn add organization members. Such organization admins and members have
access to the projects run by the organization. (For more on user roles in
CrateDB Cloud and how to set them, see our :ref:`reference for user roles
<user-roles>`_.)

Each organization has a name, a unique ID, and optionally an associated email
address. For information on how to create an organization, please refer to
our `guide to creating a new organization`_.

.. NOTE::
    Note that currently each CrateDB Cloud user corresponds to only one
    organization.


.. _concepts-projects:

Projects
========

*Projects* are contained within organizations. A project exists to contain any
number of associated services deployed in a particular region for a specific
organizational need. For example, an organization may use distinct projects to
separate between development and production environments.

A given *organization* can have any number of *projects*. Just as organizations
have administrators and members, so projects have their own administrators and
members. The two groups can but need not overlap. (Again, for more on user
roles in CrateDB Cloud and how to set them, see our :ref:`reference for user
roles <user-roles>`_.)

Each project has a name, an associated region, and a unique ID. For information
on how to create a project, please refer to our `guide to creating a new
project`_.


.. _concepts-services:

Services
========

Within each *project*, a project administrator can deploy any number of
*services*. One such service is the deployment of clusters, which can be done
through the CrateDB Cloud Console. A cluster is a set of two or more CrateDB
instances (referred to as nodes) which form a single, distributed database.
Effectively, each cluster within CrateDB Cloud is a hosted (part of) a
database. Depending on the user's subscription plan and scaling, each cluster
will have a certain storage capacity and can process a certain amount of
ingests and queries per second. Only actual cluster usage - a service within
CrateDB Cloud - is actually billed.

A cluster has a name, a unique ID, as well as a storage and processing
capacity and a number of nodes. Note that clusters are also versioned. For
information on how to deploy a cluster, please see our `tutorial for deploying
a CrateDB cluster via Azure Marketplace`_.

Clusters are not the only CrateDB Cloud service. Other offered services are -
for example - the Azure Event Hubs consumer service, which can ingest event
data from Event Hubs into CrateDB.


.. _guide to creating a new organization: https://crate.io/docs/cloud/console/en/latest/create-org.html
.. _guide to creating a new project: https://crate.io/docs/cloud/console/en/latest/create-project.html
.. _tutorial for deploying a CrateDB cluster via Azure Marketplace: https://crate.io/docs/cloud/getting-started/en/latest/getting-started/azure-to-cluster/index.html