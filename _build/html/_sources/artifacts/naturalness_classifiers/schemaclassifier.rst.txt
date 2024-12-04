.. _db_schema_classifier:

Database Schema Classifier
==========================

.. py:function:: classify_db_schema(db_name, tagged=True, db_type="ms sql")

   Classifies the naturalness of table and column names in a database schema.
   This relies on the SNAILS db_util.py or db_util_sqlite.py utilities which means
   that databases must be registered in the ./.local/dbinfo.json or dbinfo_sqlite.json files prior to use.

   :param db_name: The name of the database to classify.
   :type db_name: str
   :param tagged: Whether to tag the identifiers.
   :type tagged: bool
   :param db_type: The type of the database, either 'ms sql' or 'sqlite'.
   :type db_type: str
   :raises ModuleNotFoundError: If the snails_naturalness_classifier module is not found.
   :return: A DataFrame containing the table names, table scores, column names, column scores, and model used.
   :rtype: pd.DataFrame


.. py:function:: classify_batch_with_canine(batch_filepath)

   Classifies tables and columns in a batch file using the CanineIdentifierClassifier.

   :param batch_filepath: The file path to the batch CSV file containing table and column names.
   :type batch_filepath: str
   :return: A DataFrame containing the table names, table scores, column names, column scores, and the model used for classification. If the input DataFrame contains a 'DATABASE_NAME' column, it will also be included in the output DataFrame.
   :rtype: pd.DataFrame

.. py:function:: main()

   Main function to demonstrate the usage of the schema classification functions.  This function sets a database name, then calls the ``classify_db_schema`` function.  Commented-out lines show alternative usage scenarios.

.. toctree::
    :maxdepth: 2
    :caption: Contents: