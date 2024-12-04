.. _db_util_sqlite:

db_util_sqlite
==============



.. py:module:: db_util_sqlite

.. py:function:: do_query(query: str, database_name: str, db_list_file: str = ".local/spider_dbinfo.json") -> pandas.DataFrame

   Executes a SQL query against a SQLite database and returns the result as a Pandas DataFrame.

   :param query: The SQL query to execute.
   :type query: str
   :param database_name: The name of the database to query.
   :type database_name: str
   :param db_list_file: Path to the JSON file containing database connection information. Defaults to ".local/spider_dbinfo.json".
   :type db_list_file: str, optional
   :return: The query result as a Pandas DataFrame, or an empty DataFrame if the query returns no results.  Returns None if a ValueError occurs during DataFrame creation.
   :rtype: pandas.DataFrame or None
   :raises FileNotFoundError: If the specified database is not found in the `db_list_file`.


.. py:function:: connect_to_db(database_name: str, db_list_file: str = ".local/spider_dbinfo.json") -> sqlite3.Connection

   Establishes a connection to a SQLite database based on information provided in a JSON file.

   :param database_name: The name of the database to connect to.
   :type database_name: str
   :param db_list_file: Path to the JSON file containing database connection information. Defaults to ".local/spider_dbinfo.json".
   :type db_list_file: str, optional
   :return: A connection object to the SQLite database.
   :rtype: sqlite3.Connection
   :raises FileNotFoundError: If the specified database is not found in the `db_list_file`.


.. py:function:: get_tables_and_columns_from_sqlite_db(db_name: str, append_col_types: bool = True, table_list=None, uppercase: bool = False, schema: str = "", db_list_file: str = ".local/spider_dbinfo.json")

   Retrieves table and column information from a SQLite database.

   :param db_name: The name of the database.
   :type db_name: str
   :param append_col_types: Whether to append column types to column names. Defaults to True.
   :type append_col_types: bool, optional
   :param table_list:  Optional list of tables to retrieve information for. If None, retrieves information for all tables.
   :type table_list: list, optional
   :param uppercase: If True, converts table and column names to uppercase. Defaults to False.
   :type uppercase: bool, optional
   :param schema: Optional schema name. Not used for SQLite. Defaults to "".
   :type schema: str, optional
   :param db_list_file: Path to the JSON file containing database connection information. Defaults to ".local/spider_dbinfo.json".
   :type db_list_file: str, optional
   :return: A dictionary where keys are table names and values are lists of column names (optionally with types appended).
   :rtype: dict


.. py:function:: make_db_schema_prompt(db_name, db_type='sqlite', task='query', table_list=None, column_list=None, identifier_tags=False, use_natural_schema=False)

   Constructs a database schema prompt for use with other tools.

   :param db_name: The name of the database.
   :param db_type: The type of the database ('sqlite').
   :param task: The task for which the prompt is being generated ('query' or 'tables').
   :param table_list: A list of table names.
   :param column_list: A list of column names.
   :param identifier_tags: Whether to include identifier tags.
   :param use_natural_schema: Whether to use a natural schema.
   :return: The generated database schema prompt.


.. py:function:: get_tables_and_columns_df(tables_and_col_dict)

   Converts a dictionary of table and column information into a Pandas DataFrame.

   :param tables_and_col_dict: A dictionary where keys are table names and values are lists of column names.
   :return: A Pandas DataFrame representing the table and column information.



.. toctree::
    :maxdepth: 2
    :caption: Contents: