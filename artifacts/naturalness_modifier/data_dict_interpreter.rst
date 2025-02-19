.. _data_dict_interpreter:

data_dict_interpreter
=====================


.. py:class:: DataDictInterpreter(database_name: str = None, data_dict_file: str = None)


    This class is used to interpret a data dictionary. This is a superclass. Subclasses exist for different document types.
    

    :param database_name: The name of the database.
    :type database_name: str or None
    :param data_dict_file: The path to the data dictionary file.
    :type data_dict_file: str or None
    :ivar index: A dictionary mapping words to a list of locations in the document.
    :vartype index: defaultdict[str, list[tuple[int, int]]]
    :ivar data_dict_file: The path to the data dictionary file.
    :vartype data_dict_file: str
    :ivar filename: The name of the fewshot prompt file for a data dictionary.
    :vartype filename: str
    :ivar call_gpt: A function that takes a prompt and returns a GPT response.
    :vartype call_gpt: function


    .. py:method:: interactive_prompt_builder(num_examples: int = 5)

        User interaction method to build a fewshot prompt for a data dictionary.

        The interaction prompts the user to provide a valid database identifier for the document.
        The user is then prompted to confirm whether the generated identifier is a good example.
        If the user confirms the example is good, the example is added to the fewshot prompt.
        The user is then prompted to provide another valid database identifier for the document.
        This process repeats until the user has provided the desired number of examples.
        The user is then asked if the prompt should be saved to disk and used for the data dictionary.

        :param num_examples: The number of examples to generate for the fewshot prompt.
        :type num_examples: int
        :return: None
        :rtype: None


    .. py:method:: make_zero_shot_prompt(identifier: str, context_limit: int = 10) -> str

        Generates a zero-shot prompt for a data dictionary.

        This method generates a zero-shot prompt for a data dictionary.
        The prompt is generated using the identifier provided by the user and the context around the identifier in the data dictionary.

        :param identifier: The identifier to generate a zero-shot prompt for.
        :type identifier: str
        :param context_limit: The limit on the number of instances of the identifier referenced within the text of the data dictionary to include in the prompt.
        :type context_limit: int
        :return: A zero-shot prompt for the data dictionary.
        :rtype: str


    .. py:method:: make_few_shot_prompt(identifier: str, context_limit: int = 10, verbose: bool = True) -> str

        Generates a few-shot prompt for a data dictionary.

        :param identifier: The identifier to generate a few-shot prompt for.
        :type identifier: str
        :param context_limit: The limit on the number of instances of the identifier referenced within the text of the data dictionary to include in the prompt.
        :type context_limit: int
        :param verbose: Whether to print verbose output.
        :type verbose: bool
        :return: A few-shot prompt for the data dictionary.
        :rtype: str


    .. py:method:: getNaturalIdentifier(identifier: str, verbose: bool = False) -> str

        Returns the natural identifier for a database identifier.

        :param identifier: The identifier to get the natural identifier for.
        :type identifier: str
        :param verbose: Whether to print verbose output.
        :type verbose: bool
        :return: The natural identifier for the database identifier.
        :rtype: str


    .. py:method:: get_context_around_identifier(identifier: str, beam_width: int = None) -> list

        Returns the context around an identifier in a data dictionary.

        :param identifier: The identifier to get the context around.
        :type identifier: str
        :param beam_width: The number of characters/words to include on either side of the identifier.
        :type beam_width: int or None
        :return: A list of strings containing the context around the identifier.
        :rtype: list[str]


    .. py:method:: index_dictionary_file(file_obj) -> defaultdict

        Indexes a data dictionary file.

        :param file_obj: The file object to index.
        :type file_obj: Varies depending on subclass.
        :return: A defaultdict mapping words to a list of locations in the document.
        :rtype: defaultdict[str, list]


.. py:class:: PdfDataDictInterpreter(database_name: str = None, data_dict_file: str = None)

    This class is used to interpret a PDF data dictionary. Inherits from :py:class:`DataDictInterpreter`.

    :ivar pdf: A PdfReader object representing the PDF data dictionary.
    :vartype pdf: PdfReader
    :ivar beam_width: The number of characters to include on either side of the identifier.
    :vartype beam_width: int

    .. py:method:: get_context_around_identifier(identifier: str, beam_width: int = None) -> list
        .. :inheritdoc:: DataDictInterpreter.get_context_around_identifier

    .. py:method:: index_dictionary_file(file_obj: PdfReader) -> defaultdict
        .. :inheritdoc:: DataDictInterpreter.index_dictionary_file


.. py:class:: XmlDataDictInterpreter(database_name: str = None, data_dict_file: str = None)

    This class is used to interpret an XML data dictionary. Inherits from :py:class:`DataDictInterpreter`.

    :ivar xml_text: A string containing the text of the XML data dictionary.
    :vartype xml_text: str
    :ivar xml_list: A list of words in the XML data dictionary.
    :vartype xml_list: list[str]
    :ivar beam_width: The number of words to include on either side of the identifier.
    :vartype beam_width: int

    .. py:method:: get_context_around_identifier(identifier: str, beam_width: int = None) -> list
        .. :inheritdoc:: DataDictInterpreter.get_context_around_identifier

    .. py:method:: index_dictionary_file(file_obj) -> defaultdict
        .. :inheritdoc:: DataDictInterpreter.index_dictionary_file


.. py:class:: CsvDataDictInterpreter(database_name: str = None, data_dict_file: str = None)

    This class is used to interpret a CSV data dictionary. Inherits from :py:class:`DataDictInterpreter`.

    :ivar csv: The CSV data as a string.
    :vartype csv: str
    :ivar csv_header: The header row of the CSV.
    :vartype csv_header: str
    :ivar beam_width: The number of lines to include around the identifier.
    :vartype beam_width: int

    .. py:method:: get_context_around_identifier(identifier: str, beam_width: int = None) -> list
        .. :inheritdoc:: DataDictInterpreter.get_context_around_identifier

    .. py:method:: index_dictionary_file(file_obj) -> defaultdict
        .. :inheritdoc:: DataDictInterpreter.index_dictionary_file


.. py:class:: JsonDataDictInterpreter(database_name: str = None, data_dict_file: str = None)

    This class is used to interpret a JSON data dictionary. Inherits from :py:class:`DataDictInterpreter`.

    :ivar json_text: The JSON data as a string.
    :vartype json_text: str
    :ivar json_list: A list of words in the JSON data.
    :vartype json_list: list[str]
    :ivar beam_width: The number of words to include around the identifier.
    :vartype beam_width: int

    .. py:method:: get_context_around_identifier(identifier: str, beam_width: int = None) -> list
        .. :inheritdoc:: DataDictInterpreter.get_context_around_identifier

    .. py:method:: index_dictionary_file(file_obj) -> defaultdict
        .. :inheritdoc:: DataDictInterpreter.index_dictionary_file


.. py:class:: DataDictInterpreterFactory(database_name: str)

    Factory class for creating DataDictInterpreter objects.

    :param database_name: The name of the database.
    :type database_name: str

    .. py:method:: get_current_interpreter() -> DataDictInterpreter

        Returns the current DataDictInterpreter object.

        :return: The current DataDictInterpreter object.
        :rtype: DataDictInterpreter

    .. py:method:: get_new_interpreter(database_name: str) -> DataDictInterpreter

        Creates and returns a new DataDictInterpreter object based on the database name.

        :param database_name: The name of the database.
        :type database_name: str
        :return: A new DataDictInterpreter object.
        :rtype: DataDictInterpreter


.. toctree::
    :maxdepth: 2
    :caption: Contents: