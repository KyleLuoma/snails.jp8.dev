.. _schema_graph:

schema_graph
============


.. py:class:: SchemaGraph(database_name: str, repair_constraints: bool = True, use_single_starting_table_for_connections: bool = False)

   A class to represent a schema graph for a database.

   :param database_name: The name of the database.
   :type database_name: str
   :param repair_constraints: A flag indicating whether to repair constraints. Defaults to True.
   :type repair_constraints: bool
   :param use_single_starting_table_for_connections: A flag indicating whether to use a single starting table for connections. Defaults to False.
   :type use_single_starting_table_for_connections: bool

   :ivar manual_pkfk: A dictionary containing manual primary key and foreign key relationships for specific databases.
   :vartype manual_pkfk: dict
   :ivar database: The name of the database.
   :vartype database: str
   :ivar repair_constraints: A flag indicating whether to repair constraints.
   :vartype repair_constraints: bool
   :ivar single_starting_table: A flag indicating whether to use a single starting table for connections.
   :vartype single_starting_table: bool
   :ivar edge_type_weights: A dictionary containing weights for different types of edges.
   :vartype edge_type_weights: dict
   :ivar vertex_colors: A dictionary containing colors for different types of vertices.
   :vartype vertex_colors: dict
   :ivar pkfk_df: A DataFrame containing primary key and foreign key relationships.
   :vartype pkfk_df: pandas.DataFrame
   :ivar orphan_tables: A list of orphan tables.
   :vartype orphan_tables: list
   :ivar vertice_type_lookup: A dictionary for looking up vertex types.
   :vartype vertice_type_lookup: dict
   :ivar vertice_name_lookup: A dictionary for looking up vertex names.
   :vartype vertice_name_lookup: dict
   :ivar name_vertice_lookup: A dictionary for looking up vertex IDs by name.
   :vartype name_vertice_lookup: dict
   :ivar all_vertices: A list of all vertices.
   :vartype all_vertices: list
   :ivar edges: A list of edges in the graph.
   :vartype edges: list
   :ivar edge_type_lookup: A dictionary for looking up edge types.
   :vartype edge_type_lookup: dict
   :ivar edge_weight_lookup: A dictionary for looking up edge weights.
   :vartype edge_weight_lookup: dict
   :ivar schema_graph: The schema graph.
   :vartype schema_graph: igraph.Graph


   .. py:method:: _construct_graph() -> igraph.Graph

      Constructs the schema graph.

      :return: The schema graph.
      :rtype: igraph.Graph


   .. py:method:: _construct_pkfk_dataframe() -> pandas.DataFrame

      Constructs the primary key and foreign key DataFrame.

      :return: The primary key and foreign key DataFrame.
      :rtype: pandas.DataFrame


   .. py:method:: _construct_orphan_table_list(pkfk_df: pandas.DataFrame = None) -> list

      Constructs the list of orphan tables.

      :param pkfk_df: The primary key and foreign key DataFrame. Defaults to None.
      :type pkfk_df: pandas.DataFrame
      :return: The list of orphan tables.
      :rtype: list


   .. py:method:: _construct_vertice_lookup_dicts(pkfk_df: pandas.DataFrame = None, orphans: list = None) -> dict

      Constructs dictionaries for vertex lookups.

      :param pkfk_df: The primary key and foreign key DataFrame. Defaults to None.
      :type pkfk_df: pandas.DataFrame
      :param orphans: The list of orphan tables. Defaults to None.
      :type orphans: list
      :return: A dictionary containing vertex lookup dictionaries.
      :rtype: dict


   .. py:method:: _construct_edges(pkfk_df: pandas.DataFrame = None, all_vertices: list = None, name_vertice_lookup: dict = None, vertice_name_lookup: dict = None) -> dict

      Constructs the edges of the graph.

      :param pkfk_df: The primary key and foreign key DataFrame. Defaults to None.
      :type pkfk_df: pandas.DataFrame
      :param all_vertices: The list of all vertices. Defaults to None.
      :type all_vertices: list
      :param name_vertice_lookup: The dictionary for looking up vertex IDs by name. Defaults to None.
      :type name_vertice_lookup: dict
      :param vertice_name_lookup: The dictionary for looking up vertex names. Defaults to None.
      :type vertice_name_lookup: dict
      :return: A dictionary containing edge data.
      :rtype: dict


   .. py:method:: _repair_constraints(pkfk_df: pandas.DataFrame) -> pandas.DataFrame

      Repairs constraints in the primary key and foreign key DataFrame.

      :param pkfk_df: The primary key and foreign key DataFrame.
      :type pkfk_df: pandas.DataFrame
      :return: The repaired primary key and foreign key DataFrame.
      :rtype: pandas.DataFrame


   .. py:method:: get_schema_identifiers_between_tables(table_names: list) -> dict

      Gets schema identifiers between tables.

      :param table_names: A list of table names.
      :type table_names: list
      :return: A dictionary where keys are table names and values are lists of column names.
      :rtype: dict


   .. py:method:: get_table_connections(table_names: list) -> dict

      Gets table connections.

      :param table_names: A list of table names.
      :type table_names: list
      :return: A dictionary containing connection information.
      :rtype: dict


   .. py:method:: get_connecting_vertices_and_edges(vertices: list, single_starting_table: bool = None) -> dict

      Gets connecting vertices and edges.

      :param vertices: A list of vertices.
      :type vertices: list
      :param single_starting_table: Whether to use a single starting table. Defaults to None.
      :type single_starting_table: bool
      :return: A dictionary containing connecting vertices and edges.
      :rtype: dict



.. toctree::
    :maxdepth: 2
    :caption: Contents: