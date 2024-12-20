.. _notebooks:

SNAILS Reproducibility Notebooks
================================

The SNAILS repository contains 10 numbered Jupyter notebooks in the root of the project.
Notebooks 1 - 3 must be run in-sequence. Notebooks 4 - 10 may be run in any order.

Before running any notebooks, you must install dependences (:ref:`installing`) and instantiate the SNAILS databases (:ref:`databases`).

1. `Run NL-to-SQL Inference and Auto Scoring <https://github.com/KyleLuoma/SNAILS/blob/main/01-SNAILS-NL-to-SQL-Inference-and-Scoring.ipynb>`_: Generates and evaluates SQL queries for both execution accuracy and schema linking performance. Outputs to ``./data/nl-to-sql-performance_annotations/pending_evaluation/``.
    NOTE: After running notebook 1 and prior to running notebook 2 analysis, manually review the generated SQL using the manual validation tool (:ref:`manual_validation`).
2. `Run Statistical Tests and Create Charts <https://github.com/KyleLuoma/SNAILS/blob/main/02-SNAILS-NL-to-SQL-results-analysis.ipynb>`_: Loads validated performance annotations from ``./data/nl-to-sql-performance_annotations/`` and generates statistical tests and charts.
3. `Run Identifier-Focused Analysis <https://github.com/KyleLuoma/SNAILS/blob/main/SNAILS-identifier-analysis.ipynb>`_: Loads validated performance annotations from ``./data/nl-to-sql-performance_annotations/`` and provides an identifier-focused schema linking performance metric.
4. `Tokenizer Analysis <https://github.com/KyleLuoma/SNAILS/blob/main/04-SNAILS-tokenizer-analysis.ipynb>`_: Tokenizes SNAILS identifiers and explores their properties.
5. `Token Naturalness Analysis <https://github.com/KyleLuoma/SNAILS/blob/main/05-SNAILS-token-naturalness-analysis.ipynb>`_: Explores the alignment of tokens to natural language.
6. `Naturalness Comparisons <https://github.com/KyleLuoma/SNAILS/blob/main/06-SNAILS-naturalness-comparisons.ipynb>`_: Compares naturalness of SNAILS, Spider, Bird, and SchemaPile.
7. `SchemaPile Naturalness <https://github.com/KyleLuoma/SNAILS/blob/main/07-schemapile-naturalness.ipynb>`_: ETL scripts for SchemaPile extraction and evaluation.
8. `CodeS Query Execution and Selection <https://github.com/KyleLuoma/SNAILS/blob/main/08a-codes_query_execution_and_selection.ipynb>`_: Augments CodeS process to select the first correct SQL.
9. `DINSQL CodeS Schema Subsetting Analysis <https://github.com/KyleLuoma/SNAILS/blob/main/08b-DINSQL-CodeS-schema-subsetting-analysis.ipynb>`_: Evaluates schema subsets generated by CodeS and DINSQL.
10. `Spider Query Analysis <https://github.com/KyleLuoma/SNAILS/blob/main/09-spider-query-analysis.ipynb>`_: Creates performance metrics for Spider DEV (Native and modified) inference.

.. toctree::
    :maxdepth: 2
    :caption: Contents: