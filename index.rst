.. SNAILS documentation master file, created by
   sphinx-quickstart on Tue Dec  3 13:41:12 2024.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

SNAILS documentation
====================


`SNAILS GitHub <https://www.github.com/kyleluoma/SNAILS>`_

SNAILS is a set of NL-to-SQL-related artifacts designed to explore the effects of schema naming on LLM-based NL-to-SQL performance. It includes a set of real-world databases and associated natural language (NL) : SQL gold query pairs, human-labeled data containing naturalness classifications the tables and columns in the database collection, a model and method for ML-based naturalness classification, and prompting strategies for improving schema identifier naturalness.

.. toctree::
   :maxdepth: 2
   :caption: Contents:

   usage/installation
   artifacts/artifacts
   natural_views/natural_views
   reproducibility/reproducibility