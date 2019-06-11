Documentation
========================================

Overview
--------

EDC allows access to data without strongly typed classes or database models. CRUD operations to your database are handled atomically. EDC also provides interfaces to modify the schema in your underlying datastore.

At a high level, this allows you to build flexible enterprise applications which do not need to recompile if the underlying schema has changed.

Integration with your application
---------------------------------

EDC can either be run as a stand alone service, or integrated into your .Net application directly. If you run EDC as a stand alone service, you can write your application in any language and use the EDC APIs to interact with your data.

- `Integrating with your .Net Application (native) <#>`_
- `Integrating with your Non-.Net Application <#>`_

EDC Server
----------

Database transactions are handled by the EDC Server. Transactions are processed on a first-come-first-serve basis. The EDC Server is also responsible for cleaning up the EDC configuration database (below) and removing old data.

EDC Configuration Database
--------------------------

EDC stores its configuration in SQL Server. During setup, the connection string to the desired configuration database must be provided. EDC will auto-deploy its schema, and pre-populate the configuration tables with source data.

- `Setup connection to SQL for configuration <#>`_

Guide
^^^^

.. toctree::
   :maxdepth: 2
   :caption: Contents:



Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
