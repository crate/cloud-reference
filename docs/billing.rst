.. _billing:

=======
Billing
=======

This page documents the way billing and related subjects are handled by CrateDB
Cloud. Since - depending on your chosen offer - billing and payment forms may
appear in different places across the CrateDB Cloud interface, this guide
should function as a single reference document for finding the information you
need about billing, invoicing, and payments.


.. _billing-principles:

Billing principles
==================

CrateDB Cloud has three general principles for billing. Firstly, we only ever
bill actual usage of any of our services. This means there are no flat fees or
minimum payments.

Secondly, we only bill for a given period. This means any usage costs are
rounded up to the nearest hour of use for Marketplace customers and to the
nearest minute of use for customers directly deploying via the CrateDB Cloud
Console.

Thirdly, we measure usage based on Database Transaction Units (DTUs). These
units represent a given combination of hardware capabilities and storage for a
given subscription plan. They function as preconfigured usage units to make
tracking your usage more convenient. This means the price you pay for any
:ref:`subscription plan <gloss-subscription-plan>` is expressed as the cost of
a given number of DTUs per minute or hour (as explained above). For more
details about DTUs, see :ref:`our explanation of subscription plans
<subscription-plans-dtus>`.


.. _billing-info:

Billing information
===================

Your billing information consists of your (company) address, credit card
details, country of residence, VAT info, and so forth. This information can be
filled out whenever you make use of an offer on CrateDB Cloud that is not free
(when you only use a free offer, the billing info page will not be visible to
you). There are several ways you can provide the necessary billing information:

* As part of deploying a cluster for a new organization. If you deploy a
  cluster that is not free, you will be prompted for your billing information
  as part of the configuration wizard.
* By using the Billing tab in the Organization overview of the CrateDB Cloud
  Console. If you have a promoted cluster deployed and the free period expires,
  you can find the Billing tab by going to the Organization overview and
  clicking the fifth tab from the left. Here you can enter your billing details
  and your billing method (credit card). See the :ref:`CrateDB Console
  walkthrough <overview-org-billing>` for more information.


.. _billing-invoicing:

Invoicing
=========

Invoicing is handled variously depending on which deployment method you use.
If you deploy your cluster directly via the CrateDB Cloud Console, you will be
invoiced at the email address you provided on `signing up with CrateDB Cloud`_.
If you use one of the marketplace offers, the invoicing is handled by the
marketplace provider in question and will be part of your general invoicing for
services via that marketplace.

Currently, for direct deployments, VAT charges for EU customers are handled by
Crate.io and are added to the invoices described above. For deployments via the
marketplaces, any VAT charges due are handled by the respective marketplace
owners (Microsoft Azure and AWS).


.. _billing-processing:

Payment processing
==================

For clusters deployed in the `regular way`_, using our CrateDB Console cluster
deployment route, payment processing is handled by `Stripe`_. For clusters
deployed through the `Microsoft Azure Marketplace`_ and the `AWS Marketplace`_,
payment is handled by Stripe on behalf of the respective marketplaces.


.. _AWS Marketplace: https://aws.amazon.com/marketplace/pp/B089M4B1ND
.. _Microsoft Azure Marketplace: https://portal.azure.com/#create/crate.cratedbcloud/preview
.. _regular way: https://crate.io/docs/cloud/tutorials/en/latest/cluster-deployment/stripe.html
.. _signing up with CrateDB Cloud:
.. _Stripe: https://stripe.com/en-de
