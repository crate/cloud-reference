.. _glossary:

========
Glossary
========

This reference article is a glossary. It is meant to provide a general overview
of terms common to CrateDB Cloud. Because it forms a counterpart to the
Glossary for CrateDB, we mainly cover terms here that are specific or primary
to CrateDB Cloud; terms particular to the whole CrateDB architecture will
appear in the CrateDB glossary instead. We hope this glossary will help you
understand the basic meaning of concepts in the CrateDB Console, documentation,
the Croud CLI, and other CrateDB Cloud-related sources. It is not meant to be a
general guide to IT or IIoT terminology.

In entries, terms used that have entries of their own are cross-referenced
through links. The entries are presented in alphabetical order.

.. rubric:: Table of contents

.. contents::
   :local:


.. _glossary-audit-log:

Audit log
---------

The Audit Log registers and displays all operations associated with a
particular :ref:`organization<glossary-org>`. This includes operations on
:ref:`users<glossary-user>`, on :ref:`clusters<glossary-cluster>`, on
:ref:`projects<glossary-project>`, and on :ref:`consumers<glossary-consumer>`.
The Audit Log can be found in the rightmost tab of the Organization overview
page in the CrateDB Cloud :ref:`Console<glossary-console>`. Only an
*organization admin* has access to the Audit Log.


.. _glossary-azure-ad:

Azure AD
--------

Azure AD (Active Directory) is Microsoft's authentication and sign-in service
for accessing Microsoft hosted services. CrateDB Cloud uses AzureAD as one of
the means of sign-up and authentication for its service. For documentation on
Azure AD, refer to the |Microsoft documentation|.


.. _glossary-cluster:

Cluster
-------

Within each :ref:`project<glossary-project>`, a project administrator can
deploy any number of :ref:`products<glossary-product>`. One such service is the
deployment of clusters, which can be done through the CrateDB Cloud Console. A
cluster is a set of two or more CrateDB instances (referred to as nodes) which
form a single, distributed database. Effectively, each cluster within CrateDB
Cloud is a hosted (part of) a database. Depending on the user's
:ref:`subscription plan<glossary-subscription-plan>` and scaling, each cluster
will have a certain storage capacity and can process a certain amount of
ingests and queries per second. Only actual cluster usage is billed.

A cluster has a name, a unique ID, as well as a storage and processing
capacity and a number of nodes. Note that clusters are also versioned. For
information on how to deploy a cluster, please see our `tutorial for deploying
a CrateDB Cloud cluster from scratch`_.


.. _glossary-console:

Console
-------

The CrateDB Cloud Console is the hosted user interface for CrateDB Cloud. It
is a fully supported, easy-to-use UI which allows customers to interact with
every aspect of the CrateDB Cloud service (subject to :ref:`user role
permissions<user-roles>`.) While CrateDB Cloud also supports a CLI for
interacting with the service, we assume use of the Console by default. Only the
Console allows deployment of a :ref:`cluster<glossary-cluster>`.

For information on how to use specific elements of the Console, refer to our
`Console overview`_.


.. _glossary-consumer:

Consumer
--------

A consumer in the sense used for CrateDB Cloud architecture and documentation
is an entity that reads event data from an :ref:`IoT<glossary-iot>` hub. It is
possible to use a consumer, such as Azure IoT Hub, with CrateDB Cloud: you can
store the data processed by the consumer on the Cloud :ref:`cluster
<glossary-cluster>`. For a tutorial on how to do this, see `this article on our
blog`_. Operations on consumers are registered in the :ref:`Audit Log
<glossary-audit-log>`.


.. _glossary-croud:

Croud
-----

Croud is the name of the CrateDB Cloud Command-Line Interface (CLI). You can
use Croud to interact with the :ref:`organization<glossary-org>`,
:ref:`projects<glossary-project>` and :ref:`products<glossary-product>` you
have access to. Croud is intended for customers who prefer a CLI to the use of
a hosted web interface such as the CrateDB Cloud :ref:`Console
<glossary-console>`. Note however that the Console is the default way to
interact with CrateDB Cloud, and currently clusters can only be deployed within
the Console. The documentation for Croud can be found under the `Croud CLI
header`_ in the Docs sidebar.


.. _glossary-DTU:

DTU
---

DTU stands for Database Transaction Unit. CrateDB Cloud uses DTUs to create
configurations (combinations) of hardware specifications for specific
:ref:`subscription plans<glossary-subscription-plan>`. The advantage is that
the customer does not need to specify every element of the hardware
configuration themselves, but can simply identify the price per DTU for a given
plan and see how it matches their use case. This makes using the CrateDB Cloud
:ref:`offer<glossary-offer>` and scaling to need easy and accessible.

For a more detailed description of the subscription plans and associated DTUs,
refer to our :ref:`documentation<subscription-plans>`.


.. _glossary-endpoint:

Endpoint
--------

An endpoint is the end or goal of a communication channel. A user or client
communicates with an endpoint via a defined method, which returns a defined set
of data. In CrateDB Cloud, different :ref:`profiles<glossary-profile>` can be
used to configure their own associated endpoints, which a user connects to via
the :ref:`Croud<glossary-croud>` CLI. For information on how to do this, see
the `Croud documentation`_.


.. _glossary-iiot:

IIoT
----

The abbreviation IIoT refers to the "Industrial Internet of Things". It is a
version of :ref:`IoT<glossary-iot>`, but specifically developed for application
in industrial manufacturing. In this context, the gathering, transfer, and
storage of data gathered by digital devices installed on machines supports
greater efficiency and automation potential in the manufacturing sector.


.. _glossary-iot:

IoT
---

IoT stands for the "Internet of Things". In essence, the Internet of Things
refers to the connecting of multiple computers or digital devices, often part
of existing appliances or physical infrastructure, in such a way that they can
communicate with one another without the need for human (inter)action. In IoT
systems, each digital device is provided with a unique ID and communicates with
other devices on that basis, in particular for the transfer and receiving of
data. When used in manufacturing and industrial applications, it is also called
:ref:`IIoT<glossary-iiot>`.


.. _glossary-offer:

Offer
-----

An offer or subscription offer is a Software-as-a-Service (:ref:`SaaS
<glossary-saas>`) product prepared for consumer purchase on a subscription
basis. CrateDB Cloud has an offer on the |Microsoft Azure Marketplace| and on
the `AWS Marketplace`_.

.. _glossary-org:

Organization
------------

Organizations represent the larger structure - for example a company - within
which CrateDB Cloud :ref:`projects<glossary-project>` and associated
:ref:`products<glossary-product>` are deployed. At the organization level there
is always at least one organization administrator, who can in turn add
organization members. Such organization admins and members have access to the
projects run by the organization. (For more on user roles in CrateDB Cloud and
how to manage them, see our :ref:`reference for user roles <user-roles>`.)

Each organization has a name, a unique ID, and optionally an associated email
address. For information on how to create an organization, please refer to
our `guide to creating a new organization`_.


.. _glossary-product:

Product
-------

A product in the sense used in CrateDB Cloud is something that uses the Cloud
service for the storage of data. It consists of either a :ref:`consumer
<glossary-consumer>` or a :ref:`cluster<glossary-cluster>` and is run within a
:ref:`project<glossary-project>` of an :ref:`organization<glossary-org>`.


.. _glossary-profile:

Profile
-------

In CrateDB Cloud's CLI, :ref:`Croud<glossary-croud>`, profiles are sets of
configuration options. They define API :ref:`endpoints<glossary-endpoint>` and
the desired output format of interaction with those endpoints. A Croud user can
create multiple profiles and switch between them as desired.


.. _glossary-project:

Project
-------

A project is contained within an :ref:`organization<glossary-org>`. A project
exists to contain any number of associated services (see :ref:`products
<glossary-product>`) deployed in a particular :ref:`region<glossary-region>`
for a specific organizational need. For example, an organization may use
distinct projects to separate between development and production environments.

A given organization can have any number of projects. Just as organizations
have administrators and members, so projects have their own administrators and
members. The two groups can but need not overlap. (For more on user roles in
CrateDB Cloud and how to manage them, see our :ref:`reference for user roles
<user-roles>`.)

Each project has a name, an associated region, and a unique ID. For information
on how to create a project, please refer to our `guide to creating a new
project`_.


.. _glossary-region:

Region
------

A region in the sense used for CrateDB Cloud is a set of data centers (servers)
grouped together on a geographic basis so as to not exceed a certain latency.
CrateDB Cloud currently has four regions by default, but also offers the
option to define custom regions.


.. _glossary-saas:

SaaS
----

SaaS stands for "Software-as-a-Service". It refers to a model where software is
provided to customers on a :ref:`subscription<glossary-subscription>` basis,
rather than a one-off payment, and is centrally hosted. CrateDB Cloud can be
used as a service through its SaaS :ref:`offer<glossary-offer>` on |Microsoft
Azure Marketplace| and the `AWS Marketplace`_.


.. _glossary-scale-unit:

Scale unit
----------

The CrateDB Cloud :ref:`subscription plans<glossary-subscription-plan>` each
come with a number of different scale units. Each scale unit represents an
(additional) unit multiplying the specific combination of hardware capacity
that applies to that plan.

The relationship between scale units and :ref:`DTUs<glossary-DTU>` is subtle.
Each scale unit added on top of the first scale unit also represents one
*additional* DTU. However, not all plans *start* at one DTU. For more detailed
information about subscription plans, scale units, and DTUs, take a look at our
documentation on :ref:`DTUs and subscription plans<subscription-plans-dtus>`.


.. _glossary-subscription:

Subscription
------------

A subscription is - for the purposes of CrateDB Cloud - a container in which
the CrateDB Cloud service is created and managed, supported by one of our cloud
providers. In other words, once a customer signs up for a CrateDB Cloud
:ref:`offer<glossary-offer>` and a particular CrateDB Cloud :ref:`subscription
plan<glossary-subscription-plan>` via one of our cloud providers, they will
have a subscription to CrateDB Cloud through that particular cloud provider.

The billing for that particular instance of the CrateDB Cloud service is
managed per subscription. On Microsoft Azure, a given customer can have
multiple subscriptions. This can be practical in case that customer wants to
separate different instances of using the CrateDB Cloud service into different
billing accounts.


.. _glossary-subscription-plan:

Subscription plan
-----------------

CrateDB Cloud's :ref:`offer<glossary-offer>` consists of multiple subscription
plans. These plans are combinations of hardware specifications that are geared
towards particular customer use cases: lower capacity vs. higher capacity, more
storage vs. more processing power, and so forth. They can also be further
adjusted for different :ref:`scale units<glossary-scale-unit>` per plan.
Currently there are two subscription plans available on our cloud offers, with
more to come in the near future. For more information on choosing the right
subscription plan, refer to our documentation `on the subject`_.


.. _glossary-system-user:

System user
-----------

In CrateDB Cloud, there are two distinct system :ref:`users<glossary-user>`:

* One is the "SYSTEM" user in the :ref:`Audit Log<glossary-audit-log>`. This is
  an internal user that logs the results of (attempted) :ref:`scaling
  <glossary-scale-unit>` operations.

* The other is the "system" user in the CrateDB backend. For more information
  on this second user, refer to our `explanation`_ in the CrateDB Cloud
  reference.


.. _glossary-user:

User
----

A user in CrateDB Cloud is any individual account authorized to interact with
some part of an :ref:`organization<glossary-org>`'s assets. Each user has a
defined role within the organization (see our reference on `user roles`_) and
is associated with a specific email address.

.. NOTE::
    Note that currently each CrateDB Cloud user corresponds to only one
    organization.


.. _AWS Marketplace: https://aws.amazon.com/marketplace/pp/B089M4B1ND
.. _Console overview: https://crate.io/docs/cloud/reference/en/latest/overview.html
.. _Croud CLI header: https://crate.io/docs/cloud/cli/en/latest/index.html
.. _Croud documentation: https://crate.io/docs/cloud/cli/en/latest/configuration.html#manage-configuration-via-cli
.. _explanation: https://crate.io/docs/cloud/reference/en/latest/system-user.html
.. _guide to creating a new organization: https://crate.io/docs/cloud/howtos/en/latest/create-org.html
.. _guide to creating a new project: https://crate.io/docs/cloud/howtos/en/latest/create-project.html
.. _on the subject: https://crate.io/docs/cloud/reference/en/latest/subscription-plans.html
.. _this article on our blog: https://crate.io/a/connecting-azure-iot-hub-and-cratedb-cloud-for-the-ingestion-of-sensor-data/
.. _tutorial for deploying a CrateDB Cloud cluster from scratch: https://crate.io/docs/cloud/tutorials/en/latest/cluster-deployment/index.html
.. _user roles: https://crate.io/docs/cloud/reference/en/latest/user-roles.html
.. |Microsoft Azure Marketplace| raw:: html

    <a href="https://azuremarketplace.microsoft.com/en-us/marketplace/apps/crate.cratedbcloud?tab=PlansAndPrice" target="_blank">Microsoft Azure Marketplace</a>
.. |Microsoft documentation| raw:: html

    <a href="https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-whatis" target="_blank">Microsoft Documentation</a>