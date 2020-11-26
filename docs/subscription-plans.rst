.. _subscription-plans:

==================
Subscription plans
==================

When signing up for the CrateDB Cloud offer on the marketplace of our cloud
providers, you have a choice of four different plans. Each plan is
preconfigured for different use cases, depending on what your product needs
are. By presenting plans in terms of ready-made configurations of database
storage, memory, and computation capacity, the customer is spared the
complexity of finding the exact required hardware combinations themselves.

At the same time, the plans also offer flexibility, since your use case may
change. Not only is it possible to switch plans, but within a given plan you
can scale the required capacity for a cluster up or down. In order to make it
transparent and yet easy to use, this scaling is measured in terms of Database
Transaction Units (DTUs).

This reference gives a brief description of the plans and subsequently explains
the meaning and usage of DTUs for scaling and pricing within each plan. In this
way, making a suitable and effective choice of plan for CrateDB Cloud's cloud
offers will become straightforward.

.. rubric:: Table of contents

.. contents::
   :local:


.. _subscription-plans-overview:

The CrateDB Cloud subscription plans
====================================

Currently, CrateDB Cloud's offers on `Azure Marketplace`_ and
`AWS Marketplace`_ come with four different subscription plans:
**Development**, **General Purpose**, **IO Optimized**, and **Storage
Optimized**. Besides these, we also offer the CrateDB Cloud **Contract**.

* The **Development** plan is aimed at users who want to try out what CrateDB
  Cloud has to offer. It offers modest but robust storage, memory, and
  computation capacity. Although intended for setting up trial clusters to
  evaluate the product, it offers full flexibility and functionality. The
  capacity can be scaled along three scale units. Per scale unit, one DTU is
  added (or subtracted).

.. NOTE::
    Note that the Development plan is not covered by 24/7 support.

* The **General Purpose** plan suits all general use cases. This plan offers
  significant storage, memory, and computation capacity. The General Purpose
  plan can also currently be scaled between three scale units, each adding (or
  subtracting) one DTU.

* The **IO Optimized** plan is, as the name suggests, optimized for write and
  query speed. It offers double the capacity for inserts and queries per second
  of the **General Purpose** plan, but does not increase storage capacity.

* The **Storage Optimized** plan is, by contrast, suited for use cases that are
  primarily about (warm) storage and have less emphasis on querying. It offers
  half the insert and query capacity of the **General Purpose** plan, but four
  times the storage capacity.


.. _subscription-plans-contracts:

The CrateDB Cloud Contract
==========================

The **CrateDB Cloud Contract** allows you to pay for a full year's worth of the
service of your choice in advance. You purchase a certain number of DTUs for
one of the subscription plans mentioned above, and pay them up front for the
full year. Depending on the specifics of the contract chosen, it may be
possible to negotiate a discount based on the up front payment. For more
information, contact our `Sales team`_.

The process depends on whether you sign up via Azure or via AWS, as described
below:


Azure
-----

To sign a CrateDB Cloud Contract via Microsoft Azure, follow the `initial steps
for signup`_ while selecting the CrateDB Cloud Contract as your subscription
plan. This will automatically alert our Sales team, who will get in touch with
you to configure the specifics of your contract according to your needs.


AWS
---

To sign a CrateDB Cloud Contract via AWS, simply follow the link to the
`Contract page on the AWS Marketplace`_. The Contract will be visible as a
product you can subscribe to. The pricing information is indicative of the cost
of a single DTU for a given subscription plan (see the descriptions of the
plans above) for the full year.

.. image:: _assets/img/aws-contract.png

By subscribing to the CrateDB Cloud Contract product, you will automatically be
put in contact with our Sales department, which will further help you configure
the right plan and contract according to your needs.


.. _subscription-plans-dtus:

Explaining DTUs for scaling and billing
=======================================

What are DTUs and how do they work? As mentioned above, to make finding the
right combination of hardware capacity more tractable and accessible, CrateDB
Cloud's offers use DTUs. These DTUs have essentially two purposes: they allow
the user to choose the right combination of plan and scale to find the capacity
they need, and they provide clarity for the purposes of pricing. In order to
keep things simple, scaling in each plan is currently set up so that one scale
unit = one DTU, and billing is set up so that Crate.io bills only for DTUs/hour
actually used.

.. NOTE::
    Note, however, that scale units do not necessarily *start* at one DTU; for
    example the **Development** plan starts at three DTUs and then scales up to
    five DTUs.

Let's break this down further to clarify what each of these statements mean.

As seen above, CrateDB Cloud's cloud offer is divided into four plans. Each
plan has a starting scale (scale unit 1), which can be scaled up to scale unit
2 or 3. Because the hardware capacity in each plan is different, a scale unit
in the **Development** plan, for example, is of a different size (in terms of
storage, memory, and computation) than a scale unit in the **General Purpose**
plan. But scaling within each plan (i.e., scaling between the minimum capacity
for that plan and the maximum capacity for that plan) is made easy by the
division into scale units, each of which corresponds to one DTU.

An overview showing the range in terms of capacity of each plan, within which
the scaling of that plan operates, can be found on the `Azure offer page`_ and
the `AWS offer page`_ respectively. Here you can also find the price per DTU
per hour.

To summarize, the DTU approach to scaling means that although the offered plans
differ considerably in capacity both between each other and per scale unit
within each plan, the DTU system allows these different magnitudes to be
compared easily by the user.

The same principle applies to the pricing. If you scale within a plan, you will
readily know how much capacity you are getting and also how much you will pay
per hour. This is because you know the capacity of the plan, the fact that one
scale unit = one DTU, and the price per DTU/hour for that plan. This provides
both flexibility and transparency.

The precise calculations of required hardware capacity, actual usage of that
hardware, and a corresponding cost are all handled by Crate.io. The user only
needs to consider a plan, a scale within that plan, and the price in DTU/hour
that corresponds to it.


.. _azure-plans-example:

A practical example
===================

Say you have a use case where you expect to need approximately 6000 ingests per
second and want corresponding capacity in storage, without having to worry
about the precise storage size. Also, you want this to be easy to set up and
clearly priced and billed.

CrateDB Cloud's cloud offers provide a straightforward approach to such a use
case. Simply compare the plans on offer. You will quickly identify that the
desired capacity falls within the **General Purpose** plan, which begins at
2000 ingests/sec. and scales in 2000 ingests/sec. units. You therefore
subscribe to this plan and scale it up two times, from 2000 to 6000
ingests/sec.

Now you have a ready **General Purpose** plan for your cluster at scale
unit 3. Since each scale unit is currently simply one DTU, and the **General**
**Purpose** plan begins at one DTU, you will directly know that your total cost
is three DTU/hour of that plan. Of course, as always, only actual usage is
billed.


.. _azure-plans-notes:

Cautionary notes
================

For clarity and to prevent confusion, we add here a few notes of caution:

* The correspondence between one scaling unit and one DTU is provisional and
  may change in the future.
* Remember that not all plans, currently or in the future, necessarily *start*
  at one DTU. The **Development** plan currently starts at three DTUs of that
  plan. Therefore, when referring to the pricing per DTU/hour on the cloud
  offer, keep this in mind. This means the price for a single DTU/hour, as
  listed on the cloud offer pages, is not necessarily the minimum price for a
  given plan. This is true even if you do not scale further upwards, since your
  plan may start at several DTUs even without you scaling it up further.
* New plans will be offered in the future with different capacity ranges that
  may suit your use case. This reference document will then be updated
  accordingly. Plan terms and prices are subject to change.


.. _AWS Marketplace: https://aws.amazon.com/marketplace/pp/B089M4B1ND
.. _AWS offer page: https://aws.amazon.com/marketplace/pp/B089M4B1ND
.. _Azure Marketplace: https://azuremarketplace.microsoft.com/en-us/marketplace/apps/crate.cratedbcloud?tab=PlansAndPrice
.. _Azure offer page: https://azuremarketplace.microsoft.com/en-us/marketplace/apps/crate.cratedbcloud?tab=Overview
.. _Contract page on the AWS Marketplace: https://aws.amazon.com/marketplace/pp/B08KHK34RK
.. _initial steps  for signup: https://crate.io/docs/cloud/tutorials/en/latest/cluster-deployment/deploy-to-cluster-azure/signup-azure.html#using-the-cratedb-cloud-offer-on-azure-marketplace
.. _Sales team: sales@crate.io