.. _nl_to_sql_inference_and_prompt_generation:

nl_to_sql_inference_and_prompt_generation
=========================================

.. py:function:: do_single_question(original_prompt, use_database, question, xwalk_directory=None, column_naturalness=0, table_naturalness=0, log=True, filename_suffix='GPT-FT', filename_prefix='', task='query', service='openai', model_name='GPT-3.5', db_type="sql server", db_list_file=".local/dbinfo.json")

    Executes a single natural language question against a specified database using a specified AI service and generates a predicted SQL query.

    :param original_prompt: The initial prompt to be used.
    :type original_prompt: str
    :param use_database: The database to query.
    :type use_database: str
    :param question: The question to be appended to the prompt.
    :type question: str
    :param xwalk_directory: Directory for crosswalk files. Defaults to None.
    :type xwalk_directory: str, optional
    :param column_naturalness: Level of naturalness for columns. Defaults to 0.
    :type column_naturalness: int, optional
    :param table_naturalness: Level of naturalness for tables. Defaults to 0.
    :type table_naturalness: int, optional
    :param log: Whether to log the attempt. Defaults to True.
    :type log: bool, optional
    :param filename_suffix: Suffix for filenames. Defaults to 'GPT-FT'.
    :type filename_suffix: str, optional
    :param filename_prefix: Prefix for filenames. Defaults to ''.
    :type filename_prefix: str, optional
    :param task: The task to perform ('query' or 'tables'). Defaults to 'query'.
    :type task: str, optional
    :param service: The AI service to use ('openai', 'google-vertex', 'google-palm', 'code-llama-aws', 'togetherai'). Defaults to 'openai'.
    :type service: str, optional
    :param model_name: The model name to use. Defaults to 'GPT-3.5'.
    :type model_name: str, optional
    :param db_type: The type of database ('sql server' or 'sqlite'). Defaults to "sql server".
    :type db_type: str, optional
    :param db_list_file: Path to the database list file. Defaults to ".local/dbinfo.json".
    :type db_list_file: str, optional
    :return: A dictionary containing the prompt, SQL response, result dataframe, naturalness, and denaturalized response.
    :rtype: dict


.. py:function:: naturalize_prompt(schema_prompt, db_name, xwalk_directory='./db/schema-xwalks/consolidated_and_validated/', column_naturalness=0, table_naturalness=0, filename_suffix='GPT-FT', filename_prefix='')

    Naturalize the prompt by replacing table and column names with natural language names.

    :param schema_prompt: The prompt to naturalize.
    :type schema_prompt: str
    :param db_name: The name of the database on which the resulting query will be run.
    :type db_name: str
    :param xwalk_directory: The directory in which the crosswalk files are stored. Defaults to './db/schema-xwalks/consolidated_and_validated/'.
    :type xwalk_directory: str, optional
    :param column_naturalness: The level of naturalness to use for column names. Defaults to 0.
    :type column_naturalness: int, optional
    :param table_naturalness: The level of naturalness to use for table names. Defaults to 0.
    :type table_naturalness: int, optional
    :param filename_suffix: The suffix to use for the crosswalk files. Defaults to 'GPT-FT'.
    :type filename_suffix: str, optional
    :param filename_prefix: The prefix to use for the crosswalk files. Defaults to ''.
    :type filename_prefix: str, optional
    :return: A tuple containing a dictionary with the naturalness levels and the naturalized schema prompt.
    :rtype: tuple[dict, str]


.. py:function:: denaturalize_query(query, naturalness, xwalk_directory='./db/schema-xwalks/consolidated_and_validated/', db_name='PacificIslandLandbirds', filename_suffix='GPT-FT', filename_prefix='', syntax="tsql", target_naturalness="native")

    Denaturalize a query by replacing natural language table and column names with their native identifiers.

    :param query: The query to denaturalize.
    :type query: str
    :param naturalness: A dictionary with keys 'table' and 'column' and values corresponding to the naturalness level used for each.
    :type naturalness: dict
    :param xwalk_directory: The directory in which the crosswalk files are stored.
    :type xwalk_directory: str, optional
    :param db_name: The name of the database on which the resulting query will be run. Defaults to 'PacificIslandLandbirds'.
    :type db_name: str, optional
    :param filename_suffix: The suffix to use for the crosswalk files. Defaults to 'GPT-FT'.
    :type filename_suffix: str, optional
    :param filename_prefix: The prefix to use for the crosswalk files. Defaults to ''.
    :type filename_prefix: str, optional
    :param syntax: The SQL syntax to use ('tsql' or 'sqlite'). Defaults to 'tsql'.
    :type syntax: str, optional
    :param target_naturalness: The target naturalness level. Defaults to "native".
    :type target_naturalness: str, optional
    :return: The denaturalized query.
    :rtype: str


.. py:function:: log_attempt(prompt, response, result_df, database, model_name, naturalness={'table': 0, 'column': 0}, denaturalized_response=None)

    Logs the attempt to a file.

    :param prompt: The prompt used.
    :type prompt: str
    :param response: The response received.
    :type response: str
    :param result_df: The result dataframe.
    :type result_df: pandas.DataFrame
    :param database: The database used.
    :type database: str
    :param model_name: The model name used.
    :type model_name: str
    :param naturalness: The naturalness level used. Defaults to {'table': 0, 'column': 0}.
    :type naturalness: dict, optional
    :param denaturalized_response: The denaturalized response. Defaults to None.
    :type denaturalized_response: str, optional


.. py:function:: denaturalize_query_test()

    Test function for denaturalize_query.


.. py:function:: do_single_question_test()

    Test function for do_single_question.


.. toctree::
    :maxdepth: 2
    :caption: Contents: