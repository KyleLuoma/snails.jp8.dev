.. _naturalness_classifiers:

Naturalness Classifiers
=======================


.. toctree::
    :maxdepth: 2
    :caption: Contents:
    :glob:

    naturalness_classifiers/*


Classification Models
---------------------

Model performance data is logged in the ``./data/classifier-inference-results`` directory, and includes outputs and classification score calculations for the models described below. 

**Classes**

- N1: Regular
- N2: Low
- N3: Least

**The Tagging Feature**

If a model below is referred to as "tagged", it means that we employed a feature we call character tagging implemented in :ref:`tokenprocessing`. 


**Canine**

*Training*

Training was performed using the Transformers library with the Canine pretrained language model. 

We finetuned the model using an Nvidia GTX 1080 GPU with 8GiB of VRAM using transformers libraries, CUDA 12.1 and Torch 2.0.1.

*Collection 1 data*

Generation 1 used the same human-generated training data as the davinci finetune in .csv format found in ``./manual-scoring/gpt-data/``

*Collection 2 data*

Generation 2 was trained on an expanded set of training data that was generated by the davinci fine tune and curated by human researchers:
``./manual-scoring/canine2/``

*Inference*

Inference is accomplished with the CanineIdentifierClassifier class: :ref:`snails_naturalness_classifier`.

This class assumes the availability of a canine-based model trained using the steps described above.
The best-performing classifier is available on HuggingFace: https://huggingface.co/kyleluoma/SNAILS-word-naturalness-classifier


**Classification Heuristics**
Our heuristics-based approach is called Word List Matching, and is implemented in 
:ref:`word_list_matching`.

**GPT 3.5 Turbo Fewshot Classification**
No training was required for the fewshot classification approach, we simply use the OpenAI API and a pre-written completions prompt which is located at ``./prompts/fewshot-categoryexplanations.txt``.

**GPT Davinci Fine Tune | DEPRECATED**

The GPT Davinci finetuned model is no longer available from OpenAI.
We include this writeup for completeness.

*Training*

Finetuning was accomplished using the OpenAI API training endpoint.

Example command::

    openai api fine_tunes.create -t .\manual-scoring\gpt-data\train_tagged_prepared.jsonl -m davinci --suffix "tagged_classifier"

Training data is in ``./data/classifier-training-data/``

*Inference*

Inference is no longer possible.


