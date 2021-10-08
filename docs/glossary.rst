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


.. _gloss-audit-log:

Audit log
---------

The Audit Log registers and displays all operations associated with a

particular :ref:`organization <gloss-org>`. This includes operations on
:ref:`users <gloss-user>`, on :ref:`clusters <gloss-cluster>`, on
:ref:`projects <gloss-project>`, and on :ref:`consumers <gloss-consumer>`. The
Audit Log can be found in the rightmost tab of the Organization overview page
in the CrateDB Cloud :ref:`Console <gloss-console>`. Only an *organization
admin* has access to the Audit Log.

.. SEEALSO::

    :ref:`Audit Log <overview-org-audit>`

    :ref:`User Roles <user-roles>`


.. _gloss-azure-ad:

Azure AD
--------

Azure AD (Active Directory) is Microsoft's authentication and sign-in service
for accessing Microsoft hosted services. CrateDB Cloud uses AzureAD as one of
the means of sign-up and authentication for its service. For documentation on
Azure AD, refer to the `Microsoft documentation on Azure`_.

.. SEEALSO::

    `Sign up for CrateDB Cloud`_


.. _gloss-cluster:

Cluster
-------

Within each :ref:`project <gloss-project>`, a project administrator can deploy
any number of :ref:`products <gloss-product>`. One such service is the
deployment of clusters, which can be done through the CrateDB Cloud Console. A
cluster is a set of two or more CrateDB instances (referred to as nodes) which
form a single, distributed database. Effectively, each cluster within CrateDB
Cloud is a hosted (part of) a database. Depending on the user's
:ref:`subscription plan <gloss-subscription-plan>` and scaling, each cluster
will have a certain storage capacity and can process a certain amount of
ingests and queries per second. Only actual cluster usage is billed.

A cluster has a name, a unique ID, as well as a storage and processing capacity
and a number of nodes. Note that clusters are also versioned. For information
on how to deploy a cluster, please see our `tutorial for deploying a CrateDB
Cloud cluster from scratch`_.

.. SEEALSO::

    `Cluster deployment`_


.. _gloss-console:

Console
-------

The CrateDB Cloud Console is the hosted user interface for CrateDB Cloud. It is
a fully supported, easy-to-use UI which allows customers to interact with every
aspect of the CrateDB Cloud service (subject to :ref:`user role permissions
<user-roles>`.) While CrateDB Cloud also supports a CLI for interacting with
the service, we assume use of the Console by default. Only the Console allows
deployment of a :ref:`cluster <gloss-cluster>`.

For information on how to use specific elements of the Console, refer to our
:ref:`Console overview <overview>`.

.. SEEALSO::

    :ref:`Console overview <overview>`


.. _gloss-consumer:

Consumer
--------

A consumer in the sense used for CrateDB Cloud architecture and documentation
is an entity that reads event data from an :ref:`IoT <gloss-iot>` hub. It is
possible to use a consumer, such as Azure IoT Hub, with CrateDB Cloud: you can
store the data processed by the consumer on the Cloud :ref:`cluster
<gloss-cluster>`. For a tutorial on how to do this, see `this article on our
blog`_. Operations on consumers are registered in the :ref:`Audit Log
<gloss-audit-log>`.

.. SEEALSO::

    `Azure IoT tutorial`_

    :ref:`Audit Log <overview-org-audit>`


.. _gloss-croud:

Croud
-----

Croud is the name of the CrateDB Cloud Command-Line Interface (CLI). You can
use Croud to interact with the :ref:`organization <gloss-org>`, :ref:`projects
<gloss-project>` and :ref:`products <gloss-product>` you have access to. Croud
is intended for customers who prefer a CLI to the use of a hosted web interface
such as the CrateDB Cloud :ref:`Console <gloss-console>`. Note however that the
Console is the default way to interact with CrateDB Cloud, and currently
clusters can only be deployed within the Console. The documentation for Croud
can be found under `Croud CLI`_.

.. SEEALSO::

    `Croud CLI`_


.. _gloss-DTU:

DTU
---

DTU stands for Database Transaction Unit. CrateDB Cloud uses DTUs to create
configurations (combinations) of hardware specifications for specific
:ref:`subscription plans <gloss-subscription-plan>`. The advantage is that the
customer does not need to specify every element of the hardware configuration
themselves, but can simply identify the price per DTU for a given plan and see
how it matches their use case. This makes using the CrateDB Cloud :ref:`offer
<gloss-offer>` and scaling to need easy and accessible.

For a more detailed description of the subscription plans and associated DTUs,
refer to our :ref:`documentation <subscription-plans>`.

.. SEEALSO::

    :ref:`Subscription plans <subscription-plans>`


.. _gloss-edge:

Edge
----

CrateDB Edge is a hybrid cloud database solution presented by Crate.io. It
allows customers to deploy a Kubernetes cluster either on their own cloud
provider or their own local servers, using the database software and
maintenance support that CrateDB Cloud offers. It can be accessed through the
:ref:`CrateDB Cloud Console <gloss-console>`.

Currently, CrateDB Edge is available as a `public beta`_.


.. _gloss-endpoint:

Endpoint
--------

An endpoint is the end or goal of a communication channel. A user or client
communicates with an endpoint via a defined method, which returns a defined set
of data. In CrateDB Cloud, different :ref:`profiles <gloss-profile>` can be
used to configure their own associated endpoints, which a user connects to via
the :ref:`Croud <gloss-croud>` CLI. For information on how to do this, see the
`Croud documentation`_.

.. SEEALSO::

    `Croud CLI`_


.. _gloss-iiot:

IIoT
----

The abbreviation IIoT refers to the "Industrial Internet of Things". It is a
version of :ref:`IoT <gloss-iot>`, but specifically developed for application
in industrial manufacturing. In this context, the gathering, transfer, and
storage of data gathered by digital devices installed on machines supports
greater efficiency and automation potential in the manufacturing sector.


.. _gloss-iot:

IoT
---

IoT stands for the "Internet of Things". In essence, the Internet of Things
refers to the connecting of multiple computers or digital devices, often part
of existing appliances or physical infrastructure, in such a way that they can
communicate with one another without the need for human (inter)action. In IoT
systems, each digital device is provided with a unique ID and communicates with
other devices on that basis, in particular for the transfer and receiving of
data. When used in manufacturing and industrial applications, it is also called
:ref:`IIoT <gloss-iiot>`.


.. _gloss-offer:

Offer
-----

An offer or subscription offer is a Software-as-a-Service (:ref:`SaaS
<gloss-saas>`) product prepared for consumer purchase on a subscription
basis. CrateDB Cloud has an offer on the `Microsoft Azure Marketplace`_ and on
the `AWS Marketplace`_.

.. SEEALSO::

    :ref:`Subscription plans <subscription-plans>`


.. _gloss-org:

Organization
------------

Organizations represent the larger structure - for example a company - within
which CrateDB Cloud :ref:`projects <gloss-project>` and associated
:ref:`products <gloss-product>` are deployed. At the organization level there
is always at least one organization administrator, who can in turn add
organization members. Such organization admins and members have access to the
projects run by the organization. (For more on user roles in CrateDB Cloud and
how to manage them, see our :ref:`reference for user roles <user-roles>`.)

Each organization has a name, a unique ID, and optionally an associated email
address. For information on how to create an organization, please refer to our
`guide to creating a new organization`_.

.. SEEALSO::

    :ref:`Console overview <overview>`

    `Create a new organization`_

    :ref:`User roles <user-roles>`


.. _gloss-product:

Product
-------

A product in the sense used in CrateDB Cloud is something that uses the Cloud
service for the storage of data. It consists of either a :ref:`consumer
<gloss-consumer>` or a :ref:`cluster <gloss-cluster>` and is run within a
:ref:`project <gloss-project>` of an :ref:`organization <gloss-org>`.


.. _gloss-profile:

Profile
-------

In CrateDB Cloud's CLI, :ref:`Croud <gloss-croud>`, profiles are sets of
configuration options. They define API :ref:`endpoints <gloss-endpoint>` and
the desired output format of interaction with those endpoints. A Croud user can
create multiple profiles and switch between them as desired.

.. SEEALSO::

    `Croud CLI`_


.. _gloss-project:

Project
-------

A project is contained within an :ref:`organization <gloss-org>`. A project
exists to contain any number of associated services (see :ref:`products
<gloss-product>`) deployed in a particular :ref:`region <gloss-region>` for a
specific organizational need. For example, an organization may use distinct
projects to separate between development and production environments.

A given organization can have any number of projects. Just as organizations
have administrators and members, so projects have their own administrators and
members. The two groups can but need not overlap. (For more on user roles in
CrateDB Cloud and how to manage them, see our :ref:`reference for user roles
<user-roles>`.)

Each project has a name, an associated region, and a unique ID. For information
on how to create a project, please refer to our `guide to creating a new
project`_.

.. SEEALSO::

    `Create a new project`_

    :ref:`User roles <user-roles>`


.. _gloss-region:

Region
------

A region in the sense used for CrateDB Cloud is a set of data centers (servers)
grouped together on a geographic basis so as to not exceed a certain latency.
CrateDB Edge also permits the creation of custom regions. These regions are
designed to correspond to servers used by CrateDB Edge customers locally, on
which they can deploy CrateDB Cloud clusters for use in plants and other
production facilities.


.. _gloss-saas:

SaaS
----

SaaS stands for "Software-as-a-Service". It refers to a model where software is
provided to customers on a :ref:`subscription <gloss-subscription>` basis,
rather than a one-off payment, and is centrally hosted. Besides the default
option of subscribing directly, CrateDB Cloud can be used as a service through
its SaaS :ref:`offer <gloss-offer>` on `Microsoft Azure Marketplace`_ and the
`AWS Marketplace`_.

.. SEEALSO::

    `Subscribe to CrateDB Cloud`_

    `Subscribe via AWS Marketplace`_

    `Subscribe via Azure Marketplace`_


.. _gloss-scale-unit:

Scale unit
----------

The CrateDB Cloud :ref:`subscription plans <gloss-subscription-plan>` each come
with a number of different scale units. Each scale unit represents an
(additional) unit multiplying the specific combination of hardware capacity
that applies to that plan.

The relationship between scale units and :ref:`DTUs <gloss-DTU>` is subtle.
Each scale unit added on top of the first scale unit also represents one
*additional* DTU. However, not all plans *start* at one DTU. For more detailed
information about subscription plans, scale units, and DTUs, take a look at our
documentation on :ref:`DTUs and subscription plans<subscription-plans-dtus>`.

.. SEEALSO::

    `Scale your cluster`_

    :ref:`Subscription plans <subscription-plans>`


.. _gloss-subscription:

Subscription
------------

A subscription is - for the purposes of CrateDB Cloud - a container in which
the CrateDB Cloud service is created and managed. You can purchase a CrateDB
Cloud subscription by following the steps in our `tutorial`_. In the case of
our :ref:`SaaS <gloss-saas>` :ref:`offers <gloss-offer>` on the cloud provider
marketplaces, customers subscribe to CrateDB Cloud through that particular
cloud provider.

The billing for a particular instance of the CrateDB Cloud service is managed
per subscription. On Microsoft Azure, a given customer can have multiple
subscriptions. This can be practical in case that customer wants to separate
different instances of using the CrateDB Cloud service into different billing
accounts.

.. SEEALSO::

    `Subscribe to CrateDB Cloud`_

    `Subscribe via AWS Marketplace`_

    `Subscribe via Azure Marketplace`_

    :ref:`Subscription plans <subscription-plans>`


.. _gloss-subscription-plan:

Subscription plan
-----------------

CrateDB Cloud's service comes with several possible subscription plans. These
plans are combinations of hardware specifications that are geared towards
particular customer use cases: lower capacity vs. higher capacity, more storage
vs. more processing power, and so forth. They can also be further adjusted for
different :ref:`scale units <gloss-scale-unit>` per plan. Currently there are
four subscription plans available, as well as a separate contract option via
our marketplace :ref:`offers <gloss-offer>`. For more information, refer to our
documentation on `subscription plans`_.

.. SEEALSO::

    `Subscribe to CrateDB Cloud`_

    `Subscribe via AWS Marketplace`_

    `Subscribe via Azure Marketplace`_

    :ref:`Subscription plans <subscription-plans>`


.. _gloss-system-user:

System user
-----------

In CrateDB Cloud, there are two distinct system :ref:`users <gloss-user>`:

- One is the "SYSTEM" user in the :ref:`Audit Log <gloss-audit-log>`. This is
  an internal user that logs the results of (attempted) :ref:`scaling
  <gloss-scale-unit>` operations.

- The other is the "system" user in the CrateDB backend. For more information
  on this second user, refer to our :ref:`explanation <system-user>` in the
  CrateDB Cloud reference.

.. SEEALSO::

    :ref:`Audit Log <overview-org-audit>`


.. _gloss-tier:

Tier
----

In the CrateDB Cloud :ref:`subscription plans <gloss-subscription-plan>`, tiers
offer different magnitudes of the hardware composition of a given plan. For a
given ratio of storage capacity, memory, and CPUs, going up in tier allows you
to multiply the hardware values for your cluster deployment without changing
the hardware ratio.


.. _gloss-user:

User
----

A user in CrateDB Cloud is any individual account authorized to interact with
some part of an :ref:`organization's <gloss-org>` assets. Each user has a
defined role within the organization (see our reference on :ref:`user roles
<user-roles>`) and is associated with a specific email address.

.. NOTE::

    Note that currently each CrateDB Cloud user corresponds to only one
    organization.

.. SEEALSO::

    :ref:`User roles <user-roles>`


.. _Azure IoT tutorial: https://crate.io/a/azure-iot-hub-cratedb-sensor-data/
.. _AWS Marketplace: https://aws.amazon.com/marketplace/pp/B089M4B1ND
.. _Cluster deployment: https://crate.io/docs/cloud/tutorials/en/latest/cluster-deployment/index.html
.. _Create a new organization: https://crate.io/docs/cloud/howtos/en/latest/create-org.html
.. _Create a new project: https://crate.io/docs/cloud/howtos/en/latest/create-project.html
.. _Croud CLI: https://crate.io/docs/cloud/cli/en/latest/
.. _Croud documentation: https://crate.io/docs/cloud/cli/en/latest/configuration.html#manage-configuration-via-cli
.. _guide to creating a new organization: https://crate.io/docs/cloud/howtos/en/latest/create-org.html
.. _guide to creating a new project: https://crate.io/docs/cloud/howtos/en/latest/create-project.html
.. _Microsoft Azure Marketplace: https://azuremarketplace.microsoft.com/en-us/marketplace/apps/crate.cratedbcloud?tab=Overview
.. _Microsoft documentation on Azure: https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-whatis
.. _public beta: https://crate.io/a/announcing-cratedb-edge/
.. _Scale your cluster: https://crate.io/docs/cloud/howtos/en/latest/scale-cluster.html
.. _Sign up for CrateDB Cloud: https://crate.io/docs/cloud/tutorials/en/latest/sign-up.html
.. _Subscribe to CrateDB Cloud: https://crate.io/docs/cloud/tutorials/en/latest/cluster-deployment/stripe.html
.. _Subscribe via AWS Marketplace: https://crate.io/docs/cloud/tutorials/en/latest/cluster-deployment/deploy-to-cluster-marketplace/deploy-to-cluster-aws/signup-aws.html
.. _Subscribe via Azure Marketplace: https://crate.io/docs/cloud/tutorials/en/latest/cluster-deployment/deploy-to-cluster-marketplace/deploy-to-cluster-azure/signup-azure.html
.. _subscription plans: https://crate.io/docs/cloud/reference/en/latest/subscription-plans.html
.. _this article on our blog: https://crate.io/a/connecting-azure-iot-hub-and-cratedb-cloud-for-the-ingestion-of-sensor-data/
.. _tutorial for deploying a CrateDB Cloud cluster from scratch: https://crate.io/docs/cloud/tutorials/en/latest/cluster-deployment/index.html
.. _tutorial: https://crate.io/docs/cloud/tutorials/en/latest/cluster-deployment/index.html
.. _user roles: https://crate.io/docs/cloud/reference/en/latest/user-roles.html
