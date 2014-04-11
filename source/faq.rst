ObjectRocket FAQ
================


General
-------


What is ObjectRocket?
^^^^^^^^^^^^^^^^^^^^^

ObjectRocket is the next generation cloud database. We've built a
Industrial Strength platform specifically for MongoDB using state of the art
hardware, e.g. SSDs, PCIe Flash,  so that you never have to worry about
performance and instant on capacity so that you can scale instantly.


What do we manage?
^^^^^^^^^^^^^^^^^^

We manage the entire platform scaling, updating and replicating your data so
that all you need to focus on is your business. Managing and scaling a
database is hard you can spend a lot of time finding the right team and
developing your own platform or you can let us do it for you, we have years
of experience scaling platforms for fortune 100 companies and startups, we've
spent the time and capital to develop a world class solution and we provide
you a simple interface to manage your individual instance.


What about data portability?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

ObjectRocket is built upon MongoDB so your ability to move your data into
or out of ObjectRocket is only limited by your ability to migrate data from
one mongo instance to another.


What time zone is my data in?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

All ObjectRocket systems use PST.


What kind of query functionality does OR support?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

ObjectRocket is based on MongoDB and we support all of its functionality.


How can I change my DB password?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

You should be able to log in, and change it from the MongoDB command line like
you normally otherwise would:


.. code-block:: javascript

   > use kg
   switched to db kg
   > db.auth("kg","kg");
   1
   > show collections
   foo
   kg_test
   system.indexes
   system.profile
   system.users
   testCollection
   > db.addUser("kg","foooooo");
   {
        …
        "updatedExisting" : true,
        "n" : 1,
        "lastOp" : NumberLong("5820431785665757187"),
        "connectionId" : 1321217,
        "err" : null,
        "ok" : 1
   }
   {
        "_id" : ObjectId("50006b5f16af5eae22111ea2"),
        "pwd" : "c0912c08f9c04eeead65a7dd04ae2703",
        "readOnly" : false,
        "user" : "kg"
   }

Also, feel free to contact `support <mailto:support@objectrocket.com>`_.


Redundancy, Scalability, Performance
------------------------------------


Where is my data?
^^^^^^^^^^^^^^^^^

Customer data is kept on an instance based on the customers preferred zone.


How much data can I store?
^^^^^^^^^^^^^^^^^^^^^^^^^^

You can store as much data as you like. If you have defined shard keys for
your collections you can grow your data in chunks according to your plan
size. If you haven't defined shard keys then the maximum disk space you
can consume is equal to the size of one plan. It's very important to define
shard keys on the ObjectRocket system. Here is a
`good guide <http://docs.mongodb.org/manual/core/sharding-shard-key/>`_
about choosing shard keys.


How many requests am I allowed?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

You can execute as many operations per second as needed, however please
contact us if you believe you will need more than 200,000 Operations/sec.


How can I monitor performance / availability?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

You have two options for directly monitoring system performance and
availability. The ObjectRocket user interface has an entire page devoted to
performance and availability. Additionally, all performance and availability
metadata is available via the ObjectRocket API so you can easily integrate the
data with your existing systems.


Billing
-------


What are the details of the free promotional offer?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This promotional offer is only available to NEW ObjectRocket customers. Only
5GB sharded instances qualify for this promotional offer.

This promotional offer starts on Dec. 1, 2013 and ends Dec. 31st 2014. NEW
customers that sign up for ObjectRocket services during the promotional period
will receive a single 5GB shard free of charge for the FIRST 30 days upon sign
up. After the end of this promotion, standard fees for ObjectRocket services
will apply.

Your account is not billed until the end of each 30-day service period,
starting from the day you sign up. You can cancel at any time by
`emailing support <mailto:support@objectrocket.com>`_. If the account remains
open after the 30 day trial period, you will be billed standard fees for the
ObjectRocket services. For more information see our
`billing information <http://objectrocket.com/pricing>`_.

If the eligible ObjectRocket service is used in conjunction with any other
services, that service will be billed according to its standard billing
pricing.


How much does it cost?
^^^^^^^^^^^^^^^^^^^^^^

Please refer to the `pricing page <http://objectrocket.com/pricing>`_.


When will I be billed?
^^^^^^^^^^^^^^^^^^^^^^

ObjectRocket bills for instance usage one month in advance. When a change to
your set of instances occurs, your bill is automatically prorated for the
increased or decreased amount. Changes can occur when you manually add
instances or shards from our website, or automatically when RocketScale™
adds shards to an instance.

If you reduce your usage but continue to use your account, we'll apply any
credit toward your next bill. If you close your account entirely before the
end of the billing cycle, please
`contact support <mailto:support@objectrocket.com>`_ and we'll issue a refund
for any credit immediately.


What kinds of payment do you accept?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

We accept Visa, MasterCard, American Express, Diners Club, JCB.
We also offer custom billing via invoice for Enterprise plans.


How is space usage calculated?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Space utilization per instance is measured as follows::


   "Total File Size" = sum( db.stats.fileSize + db.stats.nsfile ) for each DB including admin, local, and config


fileSize includes data size, index size, extent size, some amount of file free
space buffer. "Total File Size" is listed on the
`instances page <https://app.objectrocket.com/instances>`_.

ObjectRocket's
`build of MongoDB <https://github.com/objectrocket/mongodb-2.2-objectrocket>`_
utilizes a custom file allocator that helps to minimize empty free space ahead
of actual data space so customers pay an absolute minimum. For more detail on
MongoDB space usage see the
`MongoDB docs <http://docs.mongodb.org/manual/faq/storage/>`_.


Other Questions
---------------


Where can I find your MongoDB customizations?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

ObjectRocket strives to deliver the best hosted MongoDB service possible.
As part of this, we do maintain some customizations to the software itself.
As per the AGPL, we make these available to anyone wishing to examine, run,
or otherwise participate! Find the repository in GitHub at:
https://github.com/objectrocket/
