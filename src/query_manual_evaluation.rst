.. _query_manual_evaluation:

query_manual_evaluation
=======================


.. py:function:: separate_by_line(query)

    Formats a SQL query string for better readability by adding newlines before keywords.

    :param query: The input SQL query string.
    :type query: str
    :return: The formatted query string.
    :rtype: str


.. py:function:: clean(elmnt)

    Removes set notation characters from a string.

    :param elmnt: The input string.
    :type elmnt: str
    :return: The cleaned string.
    :rtype: str


.. py:function:: evaluate_queries_in_workbook(init_file_open_dir=None, init_filename=None)

    Opens a GUI window to evaluate SQL queries stored in an Excel workbook.

    :param init_file_open_dir: Initial directory to open the workbook from. Defaults to None.
    :type init_file_open_dir: str, optional
    :param init_filename: Initial filename of the workbook to open. Defaults to None.
    :type init_filename: str, optional
    :return: The annotated workbook as a pandas DataFrame.
    :rtype: pd.DataFrame


    .. py:class:: DfVariable(tk.Variable)

        A Tkinter variable subclass to store and manage pandas DataFrames.

        :param value: The initial DataFrame value. Defaults to None.
        :type value: pd.DataFrame, optional

        .. py:method:: get()

            Returns the stored DataFrame.

            :return: The DataFrame.
            :rtype: pd.DataFrame

        .. py:method:: set(value)

            Sets the DataFrame value.

            :param value: The new DataFrame.
            :type value: pd.DataFrame


.. toctree::
    :maxdepth: 2
    :caption: Contents: