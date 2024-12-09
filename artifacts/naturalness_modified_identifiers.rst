:: _naturalness_modified_identifiers:

Naturalness-Modified Identifiers
================================

Dataset Description
-------------------

**Creation**
We created the naturalness-modified data using our :ref:`schemarenamer` artifacts. 
Each output from these tools was validated, and when necessary modified, by a human researcher.

**Dataset Description**
The data are stored as .xlsx crosswalks that map the native identifier to higher and/or lower naturalness levels.

*Columns*

+------------------+-----------------------------------------------------------------------+
|Column Name       |Description                                                            |
+==================+=======================================================================+
|native_identifier |The identifier as it exists in the SNAILS database.                    |
+------------------+-----------------------------------------------------------------------+
|table_or_columns  |Indicates if the identifier is a table or column.                      |
+------------------+-----------------------------------------------------------------------+
|source_database   |Database from which the identifier was extracted.                      |
+------------------+-----------------------------------------------------------------------+
|native_naturalness|The naturalness level of the native identifier.                        |
+------------------+-----------------------------------------------------------------------+
|N1_identifier     |The Regular (N1) variant of the native identifier.                     |
+------------------+-----------------------------------------------------------------------+
|N2_identifier     |The Low (N2) variant of the native identifier.                         |
+------------------+-----------------------------------------------------------------------+
|N3_identifier     |The Least (N3) variant of the native identifier.                       |
+------------------+-----------------------------------------------------------------------+


Dataset Download
----------------
The dataset can be accessed on our
`GitHub repository <https://github.com/KyleLuoma/SNAILS/tree/main/SNAILS_Artifacts/naturalness_modified_identifiers>`_.

.. toctree::
    :maxdepth: 2
    :caption: Contents: