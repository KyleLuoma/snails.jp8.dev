.. _db_util:


db_util
=======


.. py:module:: db_util

.. py:function:: do_query(query: str, database_name: str, debug: bool = False, convert_bytes_to_str: bool = False, db_list_file: str = ".local/dbinfo.json") -> pd.DataFrame

   Executes a SQL query on a specified database and returns the result as a pandas DataFrame.

   :param query: The SQL query to execute.
   :type query: str
   :param database_name: The name of the database to connect to.
   :type database_name: str
   :param debug: If True, prints debug information. Defaults to False.
   :type debug: bool
   :param convert_bytes_to_str: If True, converts byte values to strings using cp437 encoding. Defaults to False.
   :type convert_bytes_to_str: bool
   :param db_list_file: The path to the database list file. Defaults to ".local/dbinfo.json".
   :type db_list_file: str
   :return: A DataFrame containing the query results. If the query returns no results, an empty DataFrame is returned.
   :rtype: pd.DataFrame


.. py:function:: connect_to_db(database_name: str, db_list_file: str = '.local/dbinfo.json') -> pyodbc.Connection

   Establishes a connection to the specified database.

   :param database_name: The name of the database to connect to.
   :type database_name: str
   :param db_list_file: The path to the JSON file containing database connection information. Defaults to '.local/dbinfo.json'.
   :type db_list_file: str
   :return: A connection object to the specified database.
   :rtype: pyodbc.Connection
   :raises FileNotFoundError: If the db_list_file does not exist.
   :raises KeyError: If the database information is not found in the db_list_file.
   :raises pyodbc.Error: If there is an error connecting to the database.


.. py:function:: get_tables_and_columns_from_sql_server_db(db_name: str, append_col_types: bool = True, table_list: list = None, uppercase: bool = False, schema: str = "dbo") -> dict

   Returns a dictionary of tables and columns from a SQL Server database.

   :param db_name: The name of the database to use for the schema.
   :type db_name: str
   :param append_col_types: Whether to append the column types to the column names. Defaults to True.
   :type append_col_types: bool
   :param table_list: A list of tables to limit the request to. Defaults to None.
   :type table_list: list or None
   :param uppercase: Whether to return table and column names in uppercase. Defaults to False.
   :type uppercase: bool
   :param schema: The database schema to query. Defaults to "dbo".
   :type schema: str
   :return: A dictionary where keys are table names and values are lists of column names.
   :rtype: dict


.. py:function:: get_tables_and_columns_df(tables_and_col_dict: dict) -> pd.DataFrame

   Converts a dictionary of tables and their columns into a pandas DataFrame.

   :param tables_and_col_dict: A dictionary where keys are table names and values are lists of column names.
   :type tables_and_col_dict: dict
   :return: A DataFrame with two columns: 'table' and 'column'.
   :rtype: pd.DataFrame


.. py:function:: make_db_schema_prompt(db_name: str, db_type: str = 'MS SQL Server', task: str = 'query', table_list: list = None, column_list: list = None, identifier_tags: bool = False, schema: str = "dbo", table_col_function = get_tables_and_columns_from_sql_server_db)

   Creates a zero-shot prompt with schema knowledge for an LLM query.

   :param db_name: The name of the database to use for the schema.
   :type db_name: str
   :param db_type: The type of database. Defaults to 'MS SQL Server'.
   :type db_type: str
   :param task: The task to be performed ('query' or 'tables'). Defaults to 'query'.
   :type task: str
   :param table_list: A list of tables to include in the prompt. Defaults to None.
   :type table_list: list or None
   :param column_list: A list of columns to include in the prompt. Defaults to None.
   :type column_list: list or None
   :param identifier_tags: Whether to include tags around table and column names. Defaults to False.
   :type identifier_tags: bool
   :param schema: The database schema to query. Defaults to "dbo".
   :type schema: str
   :param table_col_function: The function to use for retrieving table and column information. Defaults to :py:func:`get_tables_and_columns_from_sql_server_db`.
   :type table_col_function: function
   :return: The prompt to be used for the LLM query.
   :rtype: str


.. py:function:: get_table_cardinality(db_name, table_name) -> int

   Retrieves the number of rows in a specified table.

   :param db_name: The name of the database.
   :type db_name: str
   :param table_name: The name of the table.
   :type table_name: str
   :return: The number of rows in the table.
   :rtype: int


.. py:function:: get_db_tables_cardinality(db_name, save_to_temp_folder=False) -> pd.DataFrame

   Retrieves the cardinality for each table in the specified database.

   :param db_name: The name of the database.
   :type db_name: str
   :param save_to_temp_folder: If True, saves the resulting DataFrame to a CSV file. Defaults to False.
   :type save_to_temp_folder: bool
   :return: A DataFrame containing table names and their cardinalities.
   :rtype: pd.DataFrame
   :raises Exception: If there is an error retrieving the cardinality for a table.


.. toctree::
    :maxdepth: 2
    :caption: Contents: