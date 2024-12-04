.. _schemarenamer:

schemarenamer
=============

.. py:function:: main()
    
   Executes the main logic of the script. This includes classifying the database schema, performing schema renaming, and saving the results to an Excel file.

    :no-index:

.. py:function:: transform_score_df(score_df: pandas.DataFrame) -> pandas.DataFrame

   Transforms the input score DataFrame to combine table and column scores, lowercase identifiers, and remove duplicates.

   :param score_df: DataFrame containing table and column scores.
   :type score_df: pandas.DataFrame
   :return: Transformed DataFrame with combined scores.
   :rtype: pandas.DataFrame

.. py:function:: do_schema_renaming(database_name="PacificIslandLandbirds", score_lookup_file="./data/gold-data/identifier-scores-evaluated-5-9-2024.xlsx", continuous_write=False, db_type="ms sql", db_classifier_score_df=None, only_most_natural=False, verbose=True) -> pandas.DataFrame

   Renames schema identifiers (tables and columns) in a database based on human-evaluated naturalness scores.

   :param database_name: The name of the database. Defaults to "PacificIslandLandbirds".
   :type database_name: str
   :param score_lookup_file: Path to the Excel file containing human-evaluated scores. Defaults to "./data/gold-data/identifier-scores-evaluated-5-9-2024.xlsx".
   :type score_lookup_file: str
   :param continuous_write: If True, writes logs continuously. Defaults to False.
   :type continuous_write: bool
   :param db_type: The type of the database ("ms sql" or "sqlite"). Defaults to "ms sql".
   :type db_type: str
   :param db_classifier_score_df: DataFrame with classifier scores. If None, reads from score_lookup_file. Defaults to None.
   :type db_classifier_score_df: pandas.DataFrame or None
   :param only_most_natural: If True, only generates the most natural identifier. Defaults to False.
   :type only_most_natural: bool
   :param verbose: If True, prints progress information. Defaults to True.
   :type verbose: bool
   :return: DataFrame containing original and generated identifiers with scores and errors.
   :rtype: pandas.DataFrame

.. py:function:: do_fewshot_identifier_transform(identifier, naturalness, data_dict_interpreter=None, only_most_natural=False, verbose=True, gpt_model="gpt-4o") -> dict

   Transforms a given identifier to different naturalness levels using few-shot prompting and a data dictionary interpreter.

   :param identifier: The identifier to transform.
   :type identifier: str
   :param naturalness: The original naturalness level of the identifier (e.g., "N1", "N2", "N3").
   :type naturalness: str
   :param data_dict_interpreter: An instance of DataDictInterpreter for retrieving natural identifiers. Defaults to None.
   :type data_dict_interpreter: SNAILS_Artifacts.naturalness_modifier .data_dict_reader.DataDictInterpreter or None
   :param only_most_natural: If True, only generates the most natural identifier. Defaults to False.
   :type only_most_natural: bool
   :param verbose: If True, prints progress information. Defaults to True.
   :type verbose: bool
   :param gpt_model: The GPT model to use. Defaults to "gpt-4o".
   :type gpt_model: str
   :return: A dictionary containing the transformed identifiers for different naturalness levels.
   :rtype: dict


   .. toctree::
    :maxdepth: 2
    :caption: Contents: