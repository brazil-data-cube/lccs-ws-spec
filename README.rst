..
    This file is part of Land Cover Classification System Web Service Specification.
    Copyright (C) 2019-2021 INPE.

    Land Cover Classification System Web Service Specification is free software; you can redistribute it and/or modify it
    under the terms of the MIT License; see LICENSE file for more details.


============================================================
Land Cover Classification System Web Service - Specification
============================================================

.. image:: https://img.shields.io/badge/license-MIT-green
        :target: https://github.com//brazil-data-cube/lccs-ws-spec/blob/master/LICENSE
        :alt: Software License

.. image:: https://img.shields.io/badge/lifecycle-maturing-blue.svg
        :target: https://www.tidyverse.org/lifecycle/#maturing
        :alt: Software Life Cycle

.. image:: https://img.shields.io/github/tag/brazil-data-cube/lccs-ws-spec.svg
        :target: https://github.com/brazil-data-cube/lccs-ws-spec/releases
        :alt: Release

.. image:: https://img.shields.io/discord/689541907621085198?logo=discord&logoColor=ffffff&color=7389D8
        :target: https://discord.com/channels/689541907621085198#
        :alt: Join us at Discord

About
=====

Currently, there are several data sets on regional, national and global scales with information on land use and land cover that aim to support a large number of applications, including the management of natural resources, climate change and its impacts, and biodiversity conservation. These data products are generated using different approaches and methodologies, which present information about different classes of the earth's surface, such as forests, agricultural plantations, among others. Initiatives that generate land use and land cover maps normally develop their own classification system, with different nomenclatures and meanings of the classes used.


In this context, the **LCCS-WS** (**L**\ and **C**\ over **C**\ lassification **S**\ystem **W**\eb **S**\ ervice) aims to provide a simple interface to access the various classification systems in use and their respective classes. Therefore, this service proposes a representation for the classification systems and provides an API to access the classes and their symbolizations. It is also possible to stablish mappings between classes of different systems.


Free and Open Source implementations based on this service can be found in the `lccs-ws <https://github.com/brazil-data-cube/lccs-ws>`_ (server) and `lccs.py <https://github.com/brazil-data-cube/lccs.py>`_ (Python client). See also the service **W**\eb **L**\and **T**\rajectory **S**\ystem (`WLTS <https://github.com/brazil-data-cube/wlts-spec>`_), which uses LCCS-WS to represent the classes associated with the features retrieved in its queries.


Repository Organization
=======================

- `api <./api>`_: LCCS Specification using `OpenAPI 3.0 <https://github.com/OAI/OpenAPI-Specification>`_.

- `jsonschemas <./jsonschemas>`_: `JSON Schema <https://json-schema.org/>`_ for the classification systems and classes.


Overview of Service Operations
==============================

- The ``/classification_systems`` operation when queried with a ``GET`` method returns the list of land use and cover classification systems available in the service. A ``POST`` request on this route allow the client to add a new classification system.

- The ``/classification_systems/{system_id_or_identifier}`` operation when queried with a ``GET`` method returns a document with full information about the classification system.

- The ``/classification_systems/{system_id_or_identifier}/classes`` operation when queried with a ``GET`` method returns the list of classes from a classification system.

- The ``/classification_systems/{system_id_or_identifier}/classes/{class_id}`` operation when queried with a ``GET`` method returns information about a class from a classification system

- The ``/classification_systems/{system_id_or_identifier}/styles`` operation when queried with a ``GET`` method returns the list of styles of the classification.

- The ``/classification_system/{system_id_or_identifier}/styles/{style_id}`` operation when queried with a ``GET`` method returns a document with the style of the classification system.

- The ``/mappings/{system_id_or_identifier_source}`` operation when queried with a ``GET`` method returns a list of available mappings for the classification system.

- The ``/mappings/{system_id_or_identifier_source}/{system_id_or_identifier_target}``: operation when queried with a ``GET`` method returns the mapping between the classification systems. A ``POST`` request on this route allow the client to add a new mapping.

Building the Documentation
==========================

Requirements
------------

The build system for the REST API documentation relies on the Node.js run-time environment:

  - `Node.js <https://nodejs.org/en/>`_ (Version 8+).

  - `ReDoc <https://github.com/Redocly/redoc>`_: generates HTML reference documentation from an OpenAPI specification file.


Build
-----

If you have Node.js installed, please, execute the following command to install the ReDoc dependency:

.. code-block:: shell

    $ npm install


After that, generate the documentation:

.. code-block:: shell

    $ npm run build


The above command will create a folder named ``dist`` with the bundled file index.html. You may open it in your web browser or may serve it with an HTTP Server.

For Python developers, you can serve the HTML with:

.. code-block:: shell

        python3.7 -m http.server 8080 --directory dist


License
=======

.. admonition::
    Copyright (C) 2019-2021 INPE.

    Land Cover Classification System Web Service is free software; you can redistribute it and/or modify it
    under the terms of the MIT License; see LICENSE file for more details.
