.. _call_google_nl:

call_google_nl
==============


.. py:function:: call_vertex(prompt: str, model: str = "gemini-1.5-pro-latest") -> str

   Calls the Vertex AI Gemini model with the given prompt.

   :param prompt: The input prompt for the LLM.
   :type prompt: str
   :param model: The name of the Gemini model to use. Defaults to "gemini-1.5-pro-latest".
   :type model: str, optional
   :return: The LLM's response text.
   :rtype: str
   :raises generation_types.StopCandidateException: If the LLM encounters a stop sequence.


.. py:function:: call_google_palm(prompt, max_attempts=10, model='text-bison', max_tokens=800, verbose=True) -> str

   Calls the Google PaLM API with the given prompt.

   :param prompt: The input prompt for the LLM.
   :type prompt: str
   :param max_attempts: The maximum number of attempts to make. Defaults to 10.
   :type max_attempts: int, optional
   :param model: The name of the PaLM model to use. Defaults to 'text-bison'.
   :type model: str, optional
   :param max_tokens: The maximum number of tokens to generate. Defaults to 800.
   :type max_tokens: int, optional
   :param verbose: Whether to print verbose output. Defaults to True.
   :type verbose: bool, optional
   :return: The LLM's response text.
   :rtype: str


.. py:function:: call_codey(prompt, max_attempts=10, model='code-bison-32k', max_tokens=800, verbose=True) -> str

   Calls the Codey API (Vertex AI Code Generation) with the given prompt.

   :param prompt: The input prompt for the LLM.
   :type prompt: str
   :param max_attempts: The maximum number of attempts to make. Defaults to 10.
   :type max_attempts: int, optional
   :param model: The name of the Codey model to use. Defaults to 'code-bison-32k'.
   :type model: str, optional
   :param max_tokens: The maximum number of tokens to generate. Defaults to 800.
   :type max_tokens: int, optional
   :param verbose: Whether to print verbose output. Defaults to True.
   :type verbose: bool, optional
   :return: The LLM's response text.
   :rtype: str


.. toctree::
    :maxdepth: 2
    :caption: Contents: