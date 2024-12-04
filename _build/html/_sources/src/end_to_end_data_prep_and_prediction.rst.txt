.. _end_to_end_data_prep_and_prediction:

End to End Data Prep and Prediction
===================================

.. py:function:: main(model: str, service: str, naturalness: str, database: str, bypass_nl_sql_inference: bool = True, db_list_file: str = ".local/dbinfo.json")
    :no-index:

    Executes the main logic for evaluating NL-to-SQL performance.

    :param model: The name of the NL-to-SQL model.
    :param service: The name of the service providing the model.
    :param naturalness: The naturalness level of the schema (e.g., "NATIVE", "N1", "N2", "N3").
    :param database: The name of the database to use.
    :param bypass_nl_sql_inference: Whether to bypass NL-to-SQL inference and load predictions from a file.
    :param db_list_file: Path to the database information JSON file.
    :raises FileNotFoundError: If bypass_nl_sql_inference is True and the predicted queries file is not found.


.. py:function:: mp_query_parse_function(query_data: tuple) -> tuple

    Parses a SQL query using an external Java tool and returns its statistics.

    :param query_data: A tuple containing the query number, the SQL query string, and the SQL dialect.
    :return: A tuple containing the query number and a dictionary of query statistics.


.. py:function:: mp_schema_linking_eval(data: tuple) -> tuple

    Evaluates schema linking by comparing gold and predicted queries.

    :param data: A tuple containing the query number, the gold query, and the predicted query.
    :return: A tuple containing the query number and a dictionary of schema linking evaluation results.


.. py:function:: nl_to_sql_generation(q_nl_df: pd.DataFrame, bypass: bool = False, naturalness: str = None, db_name: str = None, config_dict: dict = None, nat_cat_dict: dict = None, db_info: dict = None, db_list_file: str = ".local/dbinfo.json", db_util = src.util.db_util) -> pd.DataFrame

    Generates SQL queries from natural language questions.

    :param q_nl_df: DataFrame containing natural language questions and other information.
    :param bypass: Whether to bypass NL-to-SQL generation and load from file.
    :param naturalness: Naturalness level for schema elements.
    :param db_name: Name of the database.
    :param config_dict: Configuration dictionary.
    :param nat_cat_dict: Dictionary mapping naturalness levels to numeric values.
    :param db_info: Database information dictionary.
    :param db_list_file: Path to database information JSON file.
    :param db_util: Database utility module.
    :return: DataFrame with generated SQL queries.


.. toctree::
    :maxdepth: 2
    :caption: Contents: