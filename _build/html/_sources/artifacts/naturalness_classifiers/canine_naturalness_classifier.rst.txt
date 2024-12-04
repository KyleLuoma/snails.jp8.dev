Canine-Based Naturalness Classifier
===================================

.. py:class:: CanineIdentifierClassifier(identifiers=pd.DataFrame())

    A classifier for identifying word naturalness using a pre-trained text analysis model.
    Classifies words as Regular (label N1), Low (label N2), or Least (label N3) natural.

    :param identifiers: A DataFrame containing identifiers to classify.
    :type identifiers: pd.DataFrame
    :ivar model_name: The name of the model used for classification.
    :vartype model_name: str
    :ivar checkpoint: The checkpoint number of the model.
    :vartype checkpoint: int
    :ivar id2label: A dictionary mapping label IDs to label names.
    :vartype id2label: dict
    :ivar label2id: A dictionary mapping label names to label IDs.
    :vartype label2id: dict
    :ivar classifier: The sentiment analysis pipeline used for classification.
    :vartype classifier: pipeline
    :ivar identifiers: A DataFrame containing identifiers to classify.
    :vartype identifiers: pd.DataFrame


    .. py:method:: do_batch_job(ident_df: pd.DataFrame = None, save_as_excel: bool = False, make_tag: bool = True)

        Performs batch classification on the given DataFrame of identifiers.

        :param ident_df: The DataFrame of identifiers to classify. Defaults to None, in which case it uses :py:attr:`identifiers`.
        :type ident_df: pd.DataFrame or None
        :param save_as_excel: Whether to save the results as an Excel file.
        :type save_as_excel: bool
        :param make_tag: Whether to add a token tag to the text before classification.
        :type make_tag: bool
        :return: None


    .. py:method:: classify_identifier(identifier: str, make_tag: bool = True)

        Classifies a single identifier.

        :param identifier: The identifier to classify.
        :type identifier: str
        :param make_tag: Whether to add a token tag to the identifier before classification.
        :type make_tag: bool
        :return: The classification result.
        :rtype: list

.. toctree::
    :maxdepth: 2
    :caption: Contents: