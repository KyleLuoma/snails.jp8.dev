.. _natural_view_builder:

natural_view_builder
====================


.. py:class:: NaturalViewBuilder(xwalk_directory: str = "./schema-xwalks/consolidated_and_validated")

   A class used to build natural views for a database using crosswalks.

   :param xwalk_directory: The directory where the crosswalk files are stored. Defaults to "./schema-xwalks/consolidated_and_validated".
   :type xwalk_directory: str

   :ivar nat_label_lookup: A dictionary mapping naturalness levels to their labels.
   :vartype nat_label_lookup: dict
   :ivar nat_num_lookup: A dictionary mapping naturalness labels to their levels.
   :vartype nat_num_lookup: dict


.. py:method:: NaturalViewBuilder.initialize_db_nl_schema(database_name: str) -> None

   Initializes the natural language schema in the specified database.

   This method performs the following steps:

   1. Executes the SQL script to create the natural language schema.
   2. Executes the SQL script to create a within-database naturalness crosswalk

   :param database_name: The name of the database where the schema will be initialized.
   :type database_name: str
   :raises ProgrammingError: If there is an error executing the SQL script to create the schema.
   :return: None


.. py:method:: NaturalViewBuilder.populate_db_nl_tables(database_name: str, xwalk_directory: str = None) -> None

   Populates the database natural language tables with cross-references between native and natural identifiers for tables and columns.

   :param database_name: The name of the database to populate.
   :type database_name: str
   :param xwalk_directory: The directory where the crosswalk Excel file is located. If not provided, defaults to self.xwalk_directory.
   :type xwalk_directory: str, optional
   :return: None


.. py:method:: NaturalViewBuilder.create_views_in_database(database_name: str, naturalness_level: str = None) -> None

   Creates views in the specified database. If a naturalness level is provided, it creates a schema for that level and builds the views within that schema. Otherwise, it builds the views in the default schema.

   :param database_name: The name of the database where views will be created.
   :type database_name: str
   :param naturalness_level: The level of naturalness for the views. Defaults to None.
   :type naturalness_level: str, optional
   :return: None


.. py:method:: NaturalViewBuilder.build_natural_view_queries(database_name: str, target_schema: str = "dbo", xwalk_directory: str = None, view_schema_name: str = "db_nl", naturalness_level: str = "N1", xwalk_df: pandas.DataFrame = None) -> list

   Builds SQL queries to create natural views for tables in a SQL Server database.

   :param database_name: The name of the database to query.
   :type database_name: str
   :param target_schema: The schema of the target tables. Defaults to "dbo".
   :type target_schema: str, optional
   :param xwalk_directory: The directory containing the crosswalk files. Defaults to None.
   :type xwalk_directory: str, optional
   :param view_schema_name: The schema name for the views. Defaults to "db_nl".
   :type view_schema_name: str, optional
   :param naturalness_level: The level of naturalness for the identifiers. Defaults to "N1".
   :type naturalness_level: str, optional
   :param xwalk_df: The crosswalk dataframe. If None, it reads from the Excel file. Defaults to None.
   :type xwalk_df: pandas.DataFrame, optional
   :return: A list of SQL view creation queries.
   :rtype: list


.. toctree::
    :maxdepth: 2
    :caption: Contents: