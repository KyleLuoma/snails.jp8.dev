.. _call_llama:

call_llama
==========


.. py:function:: call_code_llama(prompt: str) -> str

   Call a Code Llama API to generate SQL queries.
   API is hosted on AWS EC2 instance using VLLM.

   :param prompt: Prompt to generate SQL query from.
   :type prompt: str
   :raises: HTTPError if the API request fails.
   :returns: Generated SQL query or "Error" if the API call fails.
   :rtype: str


.. py:data:: codellama.json

    Configuration file for the Code Llama API parameters.  This file should be a JSON file containing the following keys:

    - ``max_tokens``: Maximum number of tokens to generate. (int)
    - ``temperature``: Sampling temperature. (float)
    - ``top_p``: Top-p sampling parameter. (float)
    - ``n``: Number of sequences to generate. (int)
    - ``frequency_penalty``: Frequency penalty. (float)
    - ``presence_penalty``: Presence penalty. (float)
    - ``aws_url``: URL of the Code Llama API endpoint. (str)

    Example::

        {
          "max_tokens": 2048,
          "temperature": 0,
          "top_p": 1,
          "n": 1,
          "frequency_penalty": 0,
          "presence_penalty": 0,
          "aws_url": "http://<public IPv4 address>:8000/generate"
        }

.. toctree::
    :maxdepth: 2
    :caption: Contents: