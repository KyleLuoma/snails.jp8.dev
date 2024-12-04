.. _calltogetherai:


calltogetherai
==============


.. py:function:: call_togetherai(prompt, model)

   Calls the Together.ai API to generate a response to a given prompt.

   :param prompt: The prompt to send to the API.
   :type prompt: str
   :param model: The name of the model to use.  Should be one of the keys in the ``model_lookup_dict``.
   :type model: str
   :return: The generated response content.
   :rtype: str
   :raises FileNotFoundError: If the ".local/togetherai.json" file is not found.
   :raises json.JSONDecodeError: If the ".local/togetherai.json" file contains invalid JSON.
   :raises Exception: If there is an error communicating with the Together.ai API or processing the response.



.. toctree::
    :maxdepth: 2
    :caption: Contents: