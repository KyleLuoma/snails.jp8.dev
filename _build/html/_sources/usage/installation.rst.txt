.. _installing:

Installing SNAILS
=================

Understanding that SNAILS is a collection of artifacts and example implementations of natural
views and other concepts, installation isn't a monolithic process with a defined path to
system start. Instead, we offer steps here to retrieve the SNAILS artifacts and install dependencies.

Start by **cloning the repository** and installing dependencies::

    git clone https://www.github.com/kyleluoma/SNAILS
    python -m venv venv
    venv/scripts/activate <or> source venv/bin/activate
    pip install -r requirements.txt

**PyTorch is required**
but we don't include it in requirements.txt. This is so that 
you can `acquire the appropriate configuration <https://pytorch.org/get-started/locally/>`_ for your own environment.

**Install the SNAILS database instances** by following the steps in :ref:`databases`

**Add your own API keys** to the following files in .local_example and move to the .local folder:

* openai.json - Required for GPT 3.5 and GPT 4o SQL inference and schema renaming
* vertex.json - Required for Gemini 1.5 pro SQL inference
* huggingface.json - Required for retrieving the schema naturalness classifier


.. toctree::
    :maxdepth: 2
    :caption: Contents:

