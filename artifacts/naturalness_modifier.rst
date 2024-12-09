.. _naturalness_modifier:

Naturalness Modifier
====================

Schema Identifier Transformation and Naturalness-Modified Identifier Generation

To better observe the effect of naturalness levels on linking performance, we create alternate versions of all identifiers in the benchmark datasets.

Naturalness modification is performed the using :ref:`schemarenamer` ``do_fewshot_identifier_transform`` function.

More natural to less natural
----------------------------
Creating a less natural version of a natural identifier is a task of abbreviation. Less natural identifiers should contain elements of the full words that they represent.

in cases of transformation from higher to lower naturalness levels, do_fewshot_identifier_transform passes the fewshot prompts in the ``./prompts/`` directory to our callgpt.call_gpt function:

Less natural to more natural
----------------------------

Less natural to more natural transformation makes use of the :ref:`data_dict_interpreter`. This program uses database metadata (xml, pdf, or csv format) and GPT fewshot prompting to expand abbreviated identifiers.


.. toctree::
    :maxdepth: 2
    :caption: Contents:

    naturalness_modifier/data_dict_interpreter