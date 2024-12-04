.. _schema_linking_eval:

schema_linking_eval
===================


.. py:function:: compare_query_schema_elements(gold: str, predicted: str, verbose: bool = False) -> dict

   Compares the schema elements (tables and columns) of two SQL queries and calculates precision, recall, and F1 score.

   :param gold: The gold standard SQL query.
   :type gold: str
   :param predicted: The predicted SQL query.
   :type predicted: str
   :param verbose: If True, prints detailed comparison results. Defaults to False.
   :type verbose: bool
   :return: A dictionary containing matching, missing, and extra tables and columns, along with precision, recall, and F1 score.
   :rtype: dict

.. py:function:: mp_compare_query_schema_elements(q_nl_df: pd.DataFrame) -> dict

   Compares query schema elements in a DataFrame using multiprocessing.

   :param q_nl_df: A DataFrame with 'query_gold', 'query_predicted', and 'number' columns.
   :type q_nl_df: pd.DataFrame
   :return: A dictionary where keys are query numbers and values are comparison results.
   :rtype: dict

.. py:function:: update_scores_in_existing_results(filename)

   Updates precision and F1 scores in an existing Excel file.

   :param filename: The path to the Excel file.
   :type filename: str

.. py:function:: compare_queries()

   Compares two example SQL queries using ``compare_query_schema_elements``.


.. toctree::
    :maxdepth: 2
    :caption: Contents: