.. _load_nl_questions:


load_nl_questions
=================


.. py:function:: load_nlq_into_df(filename: str, filepath: str = "./db/queries/") -> pandas.DataFrame

   Load natural language questions from a file into a pandas DataFrame.

   The function reads a file containing natural language questions and SQL query pairs and their associated metadata, processes the content, and returns a pandas DataFrame.  If the file specified by ``filename`` is not found in ``filepath``, the function attempts to unzip "SNAILS_Gold_Queries.zip" in the ``filepath`` directory.

   :param filename: The name of the file containing the questions.
   :type filename: str
   :param filepath: The path to the directory containing the file.
   :type filepath: str
   :default filepath: "./db/queries/"
   :raises FileNotFoundError: If the specified file is not found after attempting to unzip.
   :return: A DataFrame containing the processed questions and their metadata.  Columns include "number", "question", "hints", "notes", and "query_gold".
   :rtype: pandas.DataFrame



.. toctree::
    :maxdepth: 2
    :caption: Contents: