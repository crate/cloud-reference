.. _price-calculator:

================
Price calculator
================

The `price calculator`_ for CrateDB Cloud is a tool allowing you to estimate
the price of a suitable Cloud subscription plan for your particular use case.
The output of the price calculator depends on three things: the subscription
service (Cloud provider), the subscription plan base configuration (i.e., the
price and range of data values covered that are inherent in the plan itself),
and finally the specific data requirements for your Cloud service (covered
under :ref:`plan specs configuration <price-calculator-config>` below).

.. NOTE::

    Currently, we offer three subscription plans, each with their own base
    configuration: General Purpose, IO Optimized, and Storage Optimized.
    Additionally, we offer a Development plan for trial and testing purposes,
    but it does not offer full 24/7 Crate.io support.

.. rubric:: Table of contents

.. contents::
   :local:


.. _price-calculator-config:

The plan specs configuration
============================

The specs configuration is where the price calculator is most effective. It
allows you to specify your expected (estimated) requirements for the Cloud
service in terms of detailed specifications. The price calculator takes five
inputs for these specifications:

* The expected number of **ingests** per second. This means the number of
  sensor or machine data readings expected to be generated into the database
  per second.

* The expected number **read queries** per second. This represents a
  multiplication of the number of data points to be queried, their update
  frequency (per second), and the number of representations of each data point.

* The estimated average payload size, in kilobytes (kb).

* The desired **data retention** policy, in days. This is the number of days a
  given datum or record is to be retained in the database.

* The number of **replicas**. The offered range varies between zero and two.
  More replicas means more copies of the data stored across the nodes, thereby
  providing additional security against failure but also additional storage
  requirements.

.. NOTE::

    Short descriptions of each of these inputs are also found as tooltips on
    each next to the pricing calculator itself. For more information on the
    meaning of technical terms used here, please see our `glossary`_.

Based on your selected values for each of the inputs, the pricing calculator
automatically selects for you the most fitting plan, the best configuration
within the plan, and gives an estimate for the price of the plan per hour and
per month. As always, only actual usage will be billed, on the basis of an
hourly rate.


.. _price-calculator-provider:

The Cloud provider
==================

The Cloud provider specifies the provider of the Cloud subscription. Currently
we support Microsoft Azure and AWS as cloud providers.


.. _price-calculator-example:

An example
==========

To illustrate how the pricing calculator operates, let's give an example.
Suppose you have a use case where you have done estimations of the expected
values of each of the five inputs. (As may be clear, for the pricing calculator
to be useful, you have to at least have a rough idea of these values.)

Let's say you have five machines, each sending 200 records - with an average
size of 1kb - to the database per second. You also have three dashboards, each
expected to carry out 40 read queries per second. Finally, you want data
to be retained for a period of 14 days and two replicas. The corresponding
values for each of the inputs will then be as follows:

* The **ingest** value (per second) will be 5 × 200 = 1000.
* The **read query** value (per second) will be 3 × 40 = 120.
* The **payload** value is 1kb.
* The **data retention** period is 14 days.
* The number of **replicas** is 2.

The pricing calculator then calculates the storage needs. To do this it
multiplies the ingest and payload values and converts the seconds into
corresponding values in days, which can then be multiplied by the data
retention period. Finally, that value is multiplied by 1 plus the number of
replicas (since replicas are copies of the original data). This gives the total
required storage value in kilobytes, which is then divided by 1000000 to give
the value in GB.

In our example this would be:

1000 (ingest) × 1 (payload) × 60 (secs to mins) × 60 (mins to
hours) × 24 (hours to days) × 14 (data retention) × 3 (replicas: original plus
two copies) = 3628800000, divided by 1000000 = 3628.8 GB of storage
requirements. Based on the read query value and the storage requirements, the
pricing calculator will recommend a plan and a scale level for that plan. In
our example case, that would be General Purpose at scale unit 1.

More information about plans and scale levels can be found in :ref:`our
reference on subscription plans <subscription-plans>`.


.. _glossary: https://crate.io/docs/cloud/reference/en/latest/glossary.html
.. _price calculator: https://crate.io/products/cratedb-cloud/#cloud-calculator
