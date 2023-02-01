.. _subscription-plans:

==================
Subscription plans
==================

When signing up for the CrateDB Cloud service, you have a choice of six
different subscription plans. Each plan is preconfigured for different use
cases, depending on what your storage, and computation needs are. At the same
time, the plans also offer elasticity, since your use case may change. Within 
a given plan you can horizontally scale the compute capacity of your 
cluster up or down by adding or subtracting nodes. Limited vertical 
scaling is also possible, with storage scaling (up only). For information on
how to do this, refer to our `scaling guide`_.

The nature of our plans depends on the method of your subscription. We will
first explain the plans for the recommended subscription method, `subscribing
and deploying a cluster directly`_. Subsequently, we will provide some more
detailed information regarding plans and billing for subscriptions via our
Marketplace SaaS offers.

.. rubric:: Table of contents

.. contents::
   :local:


.. _subscription-plans-stripe:

CrateDB Cloud subscription plans
================================

The standard CrateDB Cloud deployment process offers six subscription plans,
labeled: 

- CRFREE
- CR0
- CR1
- CR2
- CR3
- CR4

Each of these plans consists of two dimensions: compute and storage. The
compute configuration is set for each plan, but can be scaled
horizontally by adding or subtracting nodes during or after deployment. 
Storage is configured separately: on deployment you can set the desired 
storage capacity for your cluster, within the range of storage capacity 
options provided for that plan. Storage can also be scaled up, but cannot be
lowered after that. To view the current plans, prices, and compute and storage
ranges, refer to our `pricing page`_.

For details on signup, cluster configuration, and cluster deployment, you can
make use of our `deployment tutorial`_.

.. NOTE::
    `CrateDB Edge`_ works differently. Since it allows hosting CrateDB Cloud
    on your local or self-service Kubernetes stack, there is no need for
    different subscription plans. You can combine CrateDB Edge with any
    suitable hardware configuration that works for your use case.

Although you can scale your cluster from a single node to as many nodes as
desired, only clusters containing 3 or more nodes are covered by our 24/7
support. You can find our CrateDB Cloud terms and conditions in our `SLA`_.

CRFREE
------

This plan is aimed at new users that want to test and evaluate our offerings.
It is perpetually free to use. Every user can deploy one Free Tier cluster in
their organization without having to add a payment method. This plan
also doesn't consume any 
:ref:`Free Credit <cloud-tutorials:free-trial-budget>` that you may have
available. They are limited to one node with 2 CPUs, 2 GiB of memory, and 4
GiB of storage.

CRFREE was made for active testing and evaluation, which is why any CRFREE
cluster deletes after 7 days of inactivity. When this happens, the user is
notified via email.

CR0
---

The CR0 plan, or Shared-resource cluster, is a special category of cluster
that allows better utilization of resources. These clusters share compute and
storage resources with other clusters in this category. Because of this, they 
offer a more cost-effective solution for smaller teams and experimental 
deployments of low-traffic applications. They are limited to one node with 2 
CPUs, 2 GiB of memory, and 4 GiB of storage.

CR1-CR4
-------

These are our base plans that offer the best performance, and the biggest
flexibility. Their specs start from 1.75 CPU, 7 GiB RAM, and 32GiB storage all
the way to 14 CPU, 55 GiB RAM, and 512 GiB storage per-node. These plans can 
be scaled to up to 9 nodes. If you need more nodes than this, feel free to
`contact us`_ at any time.

.. WARNING::

    An even number of nodes can be used for testing and development without
    issue, but is not recommended for production workloads, due to the risk of
    `split-brain syndrome`_.

.. _subscription-plans-regions:

Subscription plan regions
=========================

We currently offer three :ref:`regions <gloss-region>` for our subscriptions:
one from AWS (West Europe) and two from Azure (East US 2 and West Europe). You
can use any subscription plan in any region. Note that prices for a given plan
differ depending on the region you select. We also accept region requests, in
case your preferred region is not currently available.

.. _subscription-plans-tiers:

SaaS offer tiers
================

Besides the hardware composition described above, which outlines the ratio of
the elements CPU, RAM, and storage HD for each SaaS Marketplace subscription
plan, each such plan can have two further dimensions: tiers and nodes.

Tiers are only used for Marketplace SaaS subscriptions. Tiers are simply
multiples of each hardware composition, and therefore allow vertical scaling
within a given plan. For example, the Basic tier of the **General Purpose**
plan has 3.5 CPUs, 14 GiB of RAM, and 1 TiB of storage. The next tier of that
plan, the Pro tier, has 7 CPUs, 28 GiB of RAM, and 2 TiB of storage, and so
forth. The **Development** plan differs from the others: it has only a single
tier and allows scaling between 1-3 nodes only.

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
Cloud's SaaS offers use DTUs. These DTUs have essentially two purposes: they
allow the user to choose the right combination of plan and scale to find the
capacity they need, and they provide clarity for the purposes of pricing. In
order to keep things simple, scaling in each plan is currently set up so that
one scale unit = one node = one DTU, and billing is set up so that Crate.io
bills only for DTUs/hour actually used.

Let's break this down further to clarify what each of these statements mean.

As seen above, CrateDB Cloud's SaaS offer is divided into five plans. Each
plan has a starting number of nodes (usually 3), that can be scaled to a larger
number (between 4 and 15). Because the hardware capacity in each plan and tier
is different, a node of the **GP** plan at the **Basic** tier, for example, is
of a different size (in terms of storage, memory, and computation) than a node
in the **I/O Optimized** plan at tier Premium. But the billing for these varied
hardware compositions and scales is made easy by the fact that for any given
plan and tier, one node corresponds to one DTU. Since for SaaS Marketplace
users we bill in terms of DTUs/hour, all the different dimensions of horizontal
and vertical hardware scaling are resolved into a single measure.

An overview showing the range in terms of capacity of each SaaS plan and the
price per DTU/hour can be found on the `Azure offer page`_ and the `AWS
subscription page`_, respectively. All details about each hardware dimension,
plan, tier, and node, can also be found on the deployment screen in the CrateDB
Cloud console when deploying your cluster.

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

The **CrateDB Cloud Contract** allows you to pay for a full year's worth of 
the service of your choice in advance. You purchase a certain number of DTUs
for one of the subscription plans mentioned above, and pay them up front for 
the full year. Depending on the specifics of the contract chosen, it may be
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
put in contact with our `Sales department`_, which will further help you
configure the right plan and contract according to your needs.


.. _subscription-plans-notes:

Cautionary notes
================

For clarity, we add here a few notes of caution:

* The correspondence between one node and one DTU is provisional and may change
  in the future.
* Remember that not all SaaS plans, currently or in the future, necessarily
  *start* at one DTU. All plans except the **Development** plan currently start
  at three DTUs of that plan. Therefore, when referring to the pricing per
  DTU/hour on the SaaS Marketplace cloud offer, keep this in mind. The price
  for a single DTU/hour, as listed on the cloud offer pages, is not necessarily
  the minimum price for an hour usage of a given plan.
* New plans may be offered in the future with different capacity ranges that
  may suit your use case. This reference document will then be updated
  accordingly. Plan terms and prices are subject to change.


.. _AWS Marketplace: https://aws.amazon.com/marketplace/pp/B089M4B1ND
.. _AWS subscription page: https://aws.amazon.com/marketplace/pp/B089M4B1ND
.. _Azure Marketplace: https://azuremarketplace.microsoft.com/en-us/marketplace/apps/crate.cratedbcloud?tab=PlansAndPrice
.. _Azure offer page: https://azuremarketplace.microsoft.com/en-us/marketplace/apps/crate.cratedbcloud?tab=Overview
.. _contact us: sales@crate.io
.. _Contract page on the AWS Marketplace: https://aws.amazon.com/marketplace/pp/B08KHK34RK
.. _CrateDB Edge: https://crate.io/products/cratedb-edge/
.. _deployment tutorial: https://crate.io/docs/cloud/tutorials/en/latest/cluster-deployment/stripe.html
.. _pricing page: https://crate.io/pricing
.. _Sales department: sales@crate.io
.. _Sales team: sales@crate.io
.. _scale your cluster: https://crate.io/docs/cloud/howtos/en/latest/reconfigure-cluster.html
.. _scaling guide: https://crate.io/docs/cloud/howtos/en/latest/reconfigure-cluster.html
.. _SLA: https://crate.io/legal/service-level-agreement
.. _split-brain syndrome: https://en.wikipedia.org/wiki/Split-brain_(computing)
.. _subscribing and deploying a cluster directly: https://crate.io/docs/cloud/tutorials/en/latest/cluster-deployment/stripe.html