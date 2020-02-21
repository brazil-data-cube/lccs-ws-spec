..
    This file is part of Land Cover Classification System Web Service Specification.
    Copyright (C) 2019 INPE.

    Land Cover Classification System Web Service Specification is free software; you can redistribute it and/or modify it
    under the terms of the MIT License; see LICENSE file for more details.


============================================================
Land Cover Classification System Web Service - Specification
============================================================

.. image:: https://img.shields.io/badge/license-MIT-green
        :target: https://github.com//brazil-data-cube/lccs-ws-spec/blob/master/LICENSE
        :alt: Software License

.. image:: https://img.shields.io/badge/lifecycle-experimental-orange.svg
        :target: https://www.tidyverse.org/lifecycle/#experimental
        :alt: Software Life Cycle

.. image:: https://img.shields.io/github/tag/brazil-data-cube/lccs-ws-spec.svg
        :target: https://github.com/brazil-data-cube/lccs-ws-spec/releases
        :alt: Release

.. image:: https://badges.gitter.im/brazil-data-cube/community.png
        :target: https://gitter.im/brazil-data-cube/community#
        :alt: Join the chat


About
=====

Atualmente existem diversos conjuntos de dados em escalas regionais, nacionais e globais com informação sobre uso e cobertura da terra que visam atender a um grande número de aplicações, entre elas a gestão de recursos naturais, mudanças do clima e seus impactos e conservação da biodiversidade. Esses produtos de dados são gerados utilizando diferentes abordagens e metodologias, que apresentam informações sobre diferentes classes da superfície da terra, como florestas, plantações agrícolas, entre outras. As iniciativas que geram mapas de uso e cobertura da terra, normalmente desenvolvem seu próprio sistema de classificação, com diferentes nomenclaturas e significados das classes utilizadas.


Neste contexto, o **LCCS-WS** (**L**\ and **C**\ over **C**\ lassification **S**\ystem **Web** **S**\ ervice) tem como objetivo fornecer uma interface simples para acesso aos diversos sistemas de classificação em uso e suas respectivas classes. Portanto, esse serviço propõe uma representação para os sistemas de classificação e disponibiliza uma API para acesso às classes e suas simbolizações. Também é possível consultar mapeamentos entre classes de diferentes sistemas.


Uma implementação baseada em código aberto deste serviço encontra-se no repositório `lccs-ws <https://github.com/brazil-data-cube/lccs-ws>`_.


Repository Organization
=======================

- `api <./api>`_: LCCS Specification using `OpenAPI 3.0 <https://github.com/OAI/OpenAPI-Specification>`_.

- `jsonschemas <./jsonschemas>`_: `JSON Schema <https://json-schema.org/>`_ for the classification systems and classes.


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

For Python developers, you can serve the HTMl with:

.. code-block:: shell

        python3.7 -m http.server 8080 --directory dist

