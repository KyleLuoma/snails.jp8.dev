.. _question_query_pairs:

SNAILS NL Question - Gold SQL Query dataset
===========================================

Question - query pairs are stored as executable .sql files with questions entered as SQL comments.
Each question is delinated by a ';' expression terminator.
In this repository, we store them in a .zip file ``./queries/NL-Questions-and-Gold-Queries.zip`` to avoid inadvertent inclusion in future LLM training data sets.

If you opt to use these in your own projects, please avoid publishing them where they can be scraped.

Example pair::

    -- 5: How many events observed at least some stage of decay?
    select count(distinct Event_ID) 
    from tbl_Deadwood
    ;


To run SNAILS reproducibility scripts, you don't need to interact with or manipulate the gold query file. :ref:`load_nl_questions` handles this for you.


.. toctree::
    :maxdepth: 2
    :caption: Contents: