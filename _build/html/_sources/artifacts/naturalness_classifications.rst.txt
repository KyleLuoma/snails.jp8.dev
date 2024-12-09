SNAILS Identifier Naturalness data
==================================

Dataset Generation
------------------

We made several different attempts at schema identifier naturalness classification including human scoring, heuristics-based, and machine learning.
Ultimately, we generated a ground truth dataset by validating and, where needed, modifying labels classified by a finetuned GPT davinci classification model.
Using this dataset, we then trained a local model based on Canine that outperforms the GPT-based model.

Dataset Download
----------------
The dataset can be accessed on our
`GitHub repository <https://github.com/KyleLuoma/SNAILS/tree/main/SNAILS_Artifacts/naturalness_classifications>`_.

.. toctree::
    :maxdepth: 2
    :caption: Contents: