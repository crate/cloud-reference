.. _system-user:

===========
System user
===========

This is the Reference article for the CrateDB *system* user for CrateDB Cloud
customers.

The system user is a database user called '*system*'. In CrateDB Cloud, the
backend uses this user in order to perform Cloud cluster upgrades, backups and
scaling functions, among other things.

.. WARNING::
    The user '*system*' is essential for CrateDB Cloud to function as intended.
    While it is not normally accessible through the CrateDB Console or the
    Croud CLI, it can be accessed through the CrateDB Admin UI or any other SQL
    client. It is important not to edit or delete this user in any way.
    Otherwise, the functioning of Cloud clusters may be compromised.