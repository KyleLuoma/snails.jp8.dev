.. _semantic_compare:

semantic_compare
================


.. py:function:: record_evaluation(result_df, query_id, result, message)

   Updates the result DataFrame with the evaluation outcome.

   :param result_df: DataFrame containing query results.
   :type result_df: pandas.DataFrame
   :param query_id: Identifier of the query being evaluated.
   :type query_id: str
   :param result: The evaluation result ("TRUE", "FALSE", or "UNDETERMINED").
   :type result: str
   :param message: A message explaining the evaluation result.
   :type message: str
   :return: The updated result DataFrame.
   :rtype: pandas.DataFrame


.. py:function:: compare_gold_to_generated(gold, generated, database_name, db_type="ms-sql", db_list_file="./local/db_info.json")

   Compares gold standard and generated SQL queries for semantic equivalence.

   :param gold: The gold standard SQL query.
   :type gold: str
   :param generated: The generated SQL query.
   :type generated: str
   :param database_name: The name of the database to query.
   :type database_name: str
   :param db_type: The type of the database ("ms-sql", "sqlite", or "tsql").
   :type db_type: str, optional
   :param db_list_file: Path to the database connection information JSON file.
   :type db_list_file: str, optional
   :return: A dictionary containing the equivalence result and reason.
   :rtype: dict


.. py:function:: do_batch_compare(database_name, result_file)

   Performs a batch comparison of generated SQL queries against gold standards.

   :param database_name: The name of the database to query.
   :type database_name: str
   :param result_file: Path to the Excel file containing queries and results.
   :type result_file: str


   .. toctree::
    :maxdepth: 2
    :caption: Contents: