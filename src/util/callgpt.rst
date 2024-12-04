.. _callgpt:

callgpt
=======


.. py:function:: call_gpt(prompt, max_attempts=10, model="gpt-3.5-turbo-16k", max_tokens=None, verbose=True, delay_seconds=2)

   Calls the OpenAI GPT API with the given prompt.

   :param prompt: The prompt to send to the GPT API.
   :type prompt: str
   :param max_attempts: The maximum number of attempts to make if the API call fails. Defaults to 10.
   :type max_attempts: int
   :param model: The GPT model to use. Defaults to "gpt-3.5-turbo-16k".
   :type model: str
   :param max_tokens: The maximum number of tokens to generate. If None, uses the value from the '.local/openai.json' file.
   :type max_tokens: int or None
   :param verbose: Whether to print the GPT response. Defaults to True.
   :type verbose: bool
   :param delay_seconds: The number of seconds to wait between attempts. Defaults to 2.
   :type delay_seconds: int
   :return: The GPT response.
   :rtype: str
   :raises Exception: If the API call fails after the maximum number of attempts.


.. py:function:: get_decoded_token_list(input, model="gpt-3.5-turbo-16k")

   Encodes the given input string into tokens using the specified model's encoding and then decodes each token back to a string.

   :param input: The input string to encode.
   :type input: str
   :param model: The name of the model whose encoding should be used. Defaults to "gpt-3.5-turbo-16k".
   :type model: str
   :return: A list of decoded tokens.
   :rtype: list[str]


.. toctree::
    :maxdepth: 2
    :caption: Contents: