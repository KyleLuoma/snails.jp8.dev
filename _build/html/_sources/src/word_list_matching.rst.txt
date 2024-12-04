.. _word_list_matching:

word_list_matching
==================


.. py:module:: word_list_matching

.. py:function:: debug_print(*args, doprint=True)

    Prints arguments if the debug flag is set and doprint is True.

    :param args: Variable length argument list.
    :param doprint: Boolean flag to control printing.
    :type doprint: bool
    :raises TypeError: if doprint is not a boolean.


.. py:function:: main()

    Main function to interact with the user and calculate naturalness.

    Gets user input, tokenizes it, evaluates naturalness, and exports results.

    :no-index:


.. py:class:: NaturalnessCalculator(wordlist_file="./data/words/words", excel_file=None)

    Calculates the naturalness of words and identifiers.

    :param wordlist_file: Path to the word list file.
    :type wordlist_file: str
    :param excel_file: Path to the Excel file containing pre-calculated word vectors.
    :type excel_file: str or None


    .. py:method:: score_result(self, best_match_dict)

        Calculates a score based on edit distance and ambiguity.

        :param best_match_dict: Dictionary containing best match information.
        :type best_match_dict: dict
        :return: The calculated score.
        :rtype: float


    .. py:method:: assign_label_from_score(self, score)

        Assigns a naturalness label based on the score.

        :param score: The calculated naturalness score.
        :type score: float
        :return: The naturalness label (N1, N2, or N3).
        :rtype: str


    .. py:method:: tokenize_identifier(self, identifier, camel_case=True)

        Tokenizes an identifier string.

        :param identifier: The identifier string.
        :type identifier: str
        :param camel_case: Whether to split on camel case.
        :type camel_case: bool
        :return: A list of tokens.
        :rtype: list[str]


    .. py:method:: get_best_match(self, token=None, result_dict=None)

        Retrieves the best match for a token.

        :param token: The token to find the best match for.
        :type token: str or None
        :param result_dict: The result dictionary from evaluate_naturalness.
        :type result_dict: dict or None
        :return: A dictionary containing the best match information.
        :rtype: dict
        :raises ValueError: if neither token nor result_dict is provided.


    .. py:method:: calculate_score_and_distance_of_delim_and_composite(self, identifier)

        Calculates score and distance for delimited and composite identifiers.

        :param identifier: The identifier string.
        :type identifier: str
        :return: A tuple containing a list of words and a dictionary of scores.
        :rtype: tuple[list, dict]


    .. py:method:: _mp_batch_function(self, identifier_sublist, mp_result_dict, p_ix)

        Batch function for multiprocessing score calculation.

        :param identifier_sublist: A sublist of identifiers.
        :type identifier_sublist: list[str]
        :param mp_result_dict: A shared dictionary to store results.
        :type mp_result_dict: dict
        :param p_ix: The process index.
        :type p_ix: int


    .. py:method:: mp_calculate_score_and_distance_of_delim_and_composite(self, identifier_list, num_processes=16)

        Calculates scores and distances using multiprocessing.

        :param identifier_list: A list of identifiers.
        :type identifier_list: list[str]
        :param num_processes: The number of processes to use.
        :type num_processes: int
        :return: A list of identifiers.
        :rtype: list[str]


    .. py:method:: get_min_distance_for_single_word(self, word)

        Calculates the minimum edit distance for a single word.

        :param word: The word to calculate the distance for.
        :type word: str
        :return: The minimum edit distance.
        :rtype: int


    .. py:method:: distance_batch_function(self, word_sublist, mp_result_dict)

        Batch function for multiprocessing distance calculation.

        :param word_sublist: A sublist of words.
        :type word_sublist: list[str]
        :param mp_result_dict: A shared dictionary to store results.
        :type mp_result_dict: dict


    .. py:method:: mp_get_min_distance_for_word_list(self, word_list, num_processes=16)

        Calculates minimum distances for a word list using multiprocessing.

        :param word_list: A list of words.
        :type word_list: list[str]
        :param num_processes: The number of processes to use.
        :type num_processes: int
        :return: A dictionary of minimum distances for each word.
        :rtype: dict


    .. py:method:: find_most_natural_in_composite(self, identifier, best_score=1000000, word_list=None, score_dict=None, reparse_distance=4, min_word_len=3)

        Finds the most natural words in a composite identifier.

        :param identifier: The identifier string.
        :type identifier: str
        :param best_score: The best score found so far.
        :type best_score: int
        :param word_list: A list to store the most natural words.
        :type word_list: list or None
        :param score_dict: A dictionary to store scores for each word.
        :type score_dict: dict or None
        :param reparse_distance: The distance threshold for reparsing.
        :type reparse_distance: int
        :param min_word_len: The minimum word length to consider.
        :type min_word_len: int
        :return: A tuple containing the word list and score dictionary.
        :rtype: tuple[list, dict]


    .. py:method:: evaluate_naturalness(self, word)

        Evaluates the naturalness of a word.

        :param word: The word to evaluate.
        :type word: str
        :return: A dictionary containing naturalness information.
        :rtype: dict


    .. py:method:: iterate_possible_words(self, abbreviation)

        Generates possible word pairs from an abbreviation.

        :param abbreviation: The abbreviation string.
        :type abbreviation: str
        :return: A list of word pairs.
        :rtype: list[tuple[str, str]]


    .. py:method:: get_levenshstein_dist_dict(self, word, word_df)

        Calculates Levenshtein distances between a word and a DataFrame of words.

        :param word: The word to calculate distances from.
        :type word: str
        :param word_df: The DataFrame of words.
        :type word_df: pd.DataFrame
        :return: A tuple containing a dictionary of distances and a dictionary of statistics.
        :rtype: tuple[dict, dict]


    .. py:method:: compare_letter_order(self, short_word, long_word, first_letter_match=True)

        Compares the letter order of two words.

        :param short_word: The shorter word.
        :type short_word: str
        :param long_word: The longer word.
        :type long_word: str
        :param first_letter_match: Whether the first letters must match.
        :type first_letter_match: bool
        :return: True if the letters are in order, False otherwise.
        :rtype: bool


    .. py:method:: get_words_with_letters_in_order(self, word, word_df)

        Filters a DataFrame for words with letters in the same order as the given word.

        :param word: The word to compare against.
        :type word: str
        :param word_df: The DataFrame of words.
        :type word_df: pd.DataFrame
        :return: A filtered DataFrame.
        :rtype: pd.DataFrame


    .. py:method:: get_words_with_same_letters(self, word, word_df)

        Filters a DataFrame for words with the same letters as the given word.

        :param word: The word to compare against.
        :type word: str
        :param word_df: The DataFrame of words.
        :type word_df: pd.DataFrame
        :return: A filtered DataFrame.
        :rtype: pd.DataFrame


    .. py:method:: create_word_letter_freq_vectors(self, filename="./words/words", min_word_length=3)

        Creates word letter frequency vectors.

        :param filename: The path to the word list file.
        :type filename: str
        :param min_word_length: The minimum word length to consider.
        :type min_word_length: int
        :return: A DataFrame containing word letter frequency vectors.
        :rtype: pd.DataFrame


    .. py:method:: default_value(self)

        Returns the default value for dictionaries (0).

        :return: 0
        :rtype: int


    .. py:method:: default_value_list(self)

        Returns the default value for dictionaries (empty list).

        :return: []
        :rtype: list


.. toctree::
    :maxdepth: 2
    :caption: Contents: