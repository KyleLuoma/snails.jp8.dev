.. _query_profiler:

query_profiler
==============


.. py:class:: QueryProfiler

   A class to parse and profile queries using our java-based query parser analyzer.

   :ivar __jar_path: The path to the jar file for the query parser analyzer.
   :vartype __jar_path: str
   :ivar query: The query to be parsed and profiled.
   :vartype query: str
   :ivar tree: The tree representation of the query.
   :vartype tree: dict
   :ivar stats: The statistics of the query.
   :vartype stats: dict


   .. py:method:: profile_query(query: str) -> dict

      Parses and profiles the query.

      :param query: The query to be parsed and profiled.
      :type query: str
      :return: A dictionary containing the parse tree and statistics of the query.
      :rtype: dict


   .. py:method:: get_identifiers_and_labels(query=None, distinct=True, include_brackets=True) -> dict

      Returns a dictionary of the identifiers and labels in the query.

      :param query: The query to be parsed (optional, defaults to self.query).
      :type query: str or None
      :param distinct: Whether to return distinct identifiers (default is True).
      :type distinct: bool
      :param include_brackets: Whether to include brackets in identifiers (default is True).
      :type include_brackets: bool
      :return: A dictionary containing lists of tables, columns, logical operators, functions, and a dictionary of clauses.
      :rtype: dict


   .. py:method:: get_identifiers_and_labels_df(query=None, query_num=-1, include_brackets=True) -> pandas.DataFrame

      Returns a dataframe of the identifiers and labels in the query.

      :param query: The query to be parsed (optional, defaults to self.query).
      :type query: str or None
      :param query_num: The query number (default is -1).
      :type query_num: int
      :param include_brackets: Whether to include brackets in identifiers (default is True).
      :type include_brackets: bool
      :return: A Pandas DataFrame containing the query number, identifier type, and identifier value.
      :rtype: pandas.DataFrame


   .. py:method:: tag_query(query: str, syntax: str = "tsql") -> dict

      Tags a query's table and column names using the java-based query parser analyzer.

      :param query: The query to be tagged.
      :type query: str
      :param syntax: The syntax of the query (default is "tsql"). Available options: "tsql", "sqlite".
      :type syntax: str
      :return: A dictionary containing the tagged query, table aliases, and column aliases.
      :rtype: dict


   .. py:method:: __parse_query(query: str, syntax: str = "mssql") -> dict

      Parses a query using the java-based query parser analyzer.

      :param query: The query to be parsed.
      :type query: str
      :param syntax: The syntax of the query (default is "mssql"). Currently only "mssql" is supported.
      :type syntax: str
      :return: A dictionary containing the parse tree and statistics of the query.
      :rtype: dict


   .. py:method:: parse_tree_pretty_print(tree=None) -> None

      Prints a formatted representation of the parse tree.

      :param tree: The parse tree to print (optional, defaults to self.tree).
      :type tree: dict or None


   .. py:method:: __single_obj_dict_to_tuple(dict_in) -> tuple

      Converts a single-key dictionary to a tuple.

      :param dict_in: The dictionary to convert.
      :type dict_in: dict
      :return: A tuple containing the key and value of the input dictionary.
      :rtype: tuple


.. py:function:: tag_query_test() -> None

   Tests the ``tag_query`` method.


.. py:function:: profile_query_test() -> None

   Tests the ``profile_query`` method.


.. py:function:: print_tagged_query() -> None

   Prints a tagged query and its statistics.


.. py:function:: all_tests() -> None

   Runs all test functions.


.. toctree::
    :maxdepth: 2
    :caption: Contents: