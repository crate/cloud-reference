.. _subscription-plans:

==================
Subscription plans
==================

When signing up for the CrateDB Cloud service, you have a choice of four
different plans. Each plan is preconfigured for different use cases, depending
on what your product needs are. By presenting plans in terms of ready-made
configurations of database storage, memory, and computation capacity, the
customer is spared the complexity of finding the exact required hardware
combinations themselves.

At the same time, the plans also offer flexibility, since your use case may
change. Not only do we offer multiple plans and tiers with different
specifications, but within a given plan you can scale the required capacity for
a cluster up or down by adding or subtracting nodes within a given plan.

In order to make the costs for a given set of hardware transparent and yet easy
to use, this scaling is measured in terms of Database Transaction Units (DTUs).
The simple rule of thumb is that plans and tiers increase the price per DTU,
whereas the number of nodes represents the number of DTUs expended for an hour
of usage.

This reference gives a brief description of the plans and subsequently explains
the meaning and usage of nodes, tiers, and DTUs. This should make it easy to
choose the right setup for your CrateDB Cloud subscription.

.. NOTE::
    `CrateDB Edge`_ works differently. Since it allows hosting CrateDB Cloud
    on your local or self-service Kubernetes stack, there is no need for
    different subscription plans. You can combine CrateDB Edge with any
    suitable hardware configuration that works for your use case.

.. rubric:: Table of contents

.. contents::
   :local:


.. _subscription-plans-overview:

CrateDB Cloud subscription plans
================================

CrateDB Cloud's service comes with four different subscription plans:
**Development**, **General Purpose**, **I/O Optimized**, and **Storage
Optimized**. Besides these, we also offer the CrateDB Cloud **Contract**.

* The **Development** plan is aimed at users who want to try out what CrateDB
  Cloud has to offer. It offers modest but robust storage, memory, and
  computation capacity. Although intended for setting up trial clusters to
  evaluate the product, it offers full flexibility and functionality. The
  capacity can be scaled along three scale units. Per scale unit, one DTU is
  added (or subtracted).

.. NOTE::

    The **Development** plan is not covered by 24/7 support.

* The **General Purpose** plan suits all general use cases. This plan offers
  significant storage, memory, and computation capacity. The General Purpose
  plan can also currently be scaled between three scale units, each adding (or
  subtracting) one DTU.

* The **I/O Optimized** plan is, as the name suggests, optimized for write and
  query speed. It offers double the capacity for inserts and queries per second
  of the **General Purpose** plan, but does not increase storage capacity.

* The **Storage Optimized** plan is, by contrast, suited for use cases that are
  primarily about (warm) storage and have less emphasis on querying. It offers
  half the insert and query capacity of the **General Purpose** plan, but four
  times the storage capacity.


.. _subscription-plans-nodes:

Subscription Plan Tiers and Nodes
=================================

Besides the hardware composition described above, which outlines the ratio of
the elements CPU, RAM, and storage HD for each subscription plan, each plan has
two further dimensions: tiers and nodes.

Tiers are simply multiples of each hardware composition, and therefore allow
vertical scaling within a given plan. For example, the Basic tier of the
General Purpose plan has 3.5 CPUs, 14 GiB of RAM, and 1 TiB of storage. The
next tier of that plan, the Pro tier, has 7 CPUs, 28 GiB of RAM, and 2 TiB of
storage, and so forth.

The number of nodes in a cluster can also be adjusted manually for a given
plan. Basic tiers of a plan allow scaling between 3, 4, and 5 nodes, whereas
higher tiers allow scaling up to 15. (If you need more nodes than this, you can
`contact us`_ any time.)

.. WARNING::

    An even number of nodes can be used for testing and development without
    issue, but is not recommended for production workloads, due to the risk of
    `split-brain syndrome`_.

The Development plan differs from the others: it has only a single tier and
allows scaling between 1-3 nodes.

.. WARNING::

    When you have scaled a Development plan cluster above one node, you cannot
    scale it back down to a single node again.

Each node, in turn, corresponds to one DTU, regardless of tier. Put simply, the
tier determines the hardware 'size' of the node, the number of nodes determines
the number of DTUs at that size. Since the Development plan starts at 1 node,
it starts at 1 DTU; other plans start at 3 nodes and therefore start at 3 DTUs.

If you use our SaaS Marketplace offers, you will encounter DTUs/hour as the
measure of actual usage that we bill for. If you subscribe to CrateDB Cloud
directly via credit card, you do not have to concern yourself with DTUs. For a
more detailed explanation of DTUs, see the section below.


.. _subscription-plans-dtus:

Explaining DTUs for scaling and billing
=======================================

What are DTUs and how do they work? As mentioned above, to make finding the
right combination of hardware capacity more tractable and accessible, CrateDB
Cloud's offers use DTUs. These DTUs have essentially two purposes: they allow
the user to choose the right combination of plan and scale to find the capacity
they need, and they provide clarity for the purposes of pricing. In order to
keep things simple, scaling in each plan is currently set up so that one scale
unit = one node = one DTU, and billing is set up so that Crate.io bills only
for DTUs/hour actually used.

Let's break this down further to clarify what each of these statements mean.

As seen above, CrateDB Cloud's SaaS offer is divided into four plans. Each
plan has a starting number of nodes (usually 3), that can be scaled to a larger
number (between 4 and 15). Because the hardware capacity in each plan and tier
is different, a node of the **GP** plan at the **Basic** tier, for example, is
of a different size (in terms of storage, memory, and computation) than a node
in the I/O Optimized plan at tier Premium. But the billing for these varied
hardware compositions and scales is made easy by the fact that for any given
plan and tier, one node corresponds to one DTU. Since for SaaS Marketplace
users we bill in terms of DTUs/hour, all the different dimensions of horizontal
and vertical hardware scaling are resolved into a single measure.

An overview showing the range in terms of capacity of each plan can be found on
the `Azure offer page`_ and the `AWS subscription page`_, respectively. All
details about each hardware dimension, plan, tier, and node, can be found on
the deployment screen in the CrateDB Cloud console when deploying your cluster.
For SaaS Marketplace offers, you can also find the price per DTU/hour for each
subscription plan in the same overview.

To summarize:

The DTU approach to scaling means that although the offered plans differ
considerably in capacity per plan, tier, and number of nodes, the DTU system
allows you to easily compare these different magnitudes for a single usage
price on the SaaS Marketplaces.

The precise calculations of hardware capacity, actual usage of that hardware,
and a corresponding cost are all handled by Crate.io. The user only needs to
choose a plan, a tier within that plan, and the number of nodes. You will then
know the price in DTU/hour that corresponds to your choice.


.. _subscription-plans-contracts:

The CrateDB Cloud Contract
==========================

The **CrateDB Cloud Contract** allows you to pay for a full year's worth of the
service of your choice in advance. You purchase a certain number of DTUs for
one of the subscription plans mentioned above, and pay them up front for the
full year. Depending on the specifics of the contract chosen, it may be
possible to negotiate a discount based on the up front payment. The CrateDB
Cloud Contract is only available via our supported cloud providers on the SaaS
Marketplaces. For more information, contact our `Sales team`_.

The process depends on whether you sign up via Azure or via AWS, as described
below:


Azure
-----

To sign a CrateDB Cloud Contract via Microsoft Azure, follow the :ref:`initial
steps for signup <cloud-tutorials:signup-azure-to-cluster-offer>` while
selecting the CrateDB Cloud Contract as your subscription plan. This will
automatically alert our Sales team, who will get in touch with you to configure
the specifics of your contract according to your needs.


AWS
---

To sign a CrateDB Cloud Contract via AWS, simply follow the link to the
`Contract page on the AWS Marketplace`_. The Contract will be visible as a
product you can subscribe to. The pricing information is indicative of the cost
of a single DTU for a given subscription plan (see the descriptions of the
plans above) for the full year.

.. image:: _assets/img/aws-contract.png
   :alt: AWS Marketplace CrateDB Cloud Contract offer

By subscribing to the CrateDB Cloud Contract product, you will automatically be
put in contact with our Sales department, which will further help you configure
the right plan and contract according to your needs.


.. _subscription-plans-notes:

Cautionary notes
================

For clarity, we add here a few notes of caution:

* The correspondence between one node and one DTU is provisional and may change
  in the future.
* Remember that not all plans, currently or in the future, necessarily *start*
  at one DTU. All plans except the **Development** plan currently start at
  three DTUs of that plan. Therefore, when referring to the pricing per
  DTU/hour on the SaaS Marketplace cloud offer, keep this in mind. The price
  for a single DTU/hour, as listed on the cloud offer pages, is not necessarily
  the minimum price for an hour usage of a given plan.
* New plans may be offered in the future with different capacity ranges that
  may suit your use case. This reference document will then be updated
  accordingly. Plan terms and prices are subject to change.


.. _AWS subscription page: https://aws.amazon.com/marketplace/pp/B089M4B1ND
.. _Azure offer page: https://azuremarketplace.microsoft.com/en-us/marketplace/apps/crate.cratedbcloud?tab=Overview
.. _contact us: sales@crate.io
.. _Contract page on the AWS Marketplace: https://aws.amazon.com/marketplace/pp/B08KHK34RK
.. _CrateDB Edge: https://crate.io/products/cratedb-edge/
.. _Sales team: sales@crate.io
.. _split-brain syndrome: https://en.wikipedia.org/wiki/Split-brain_(computing)