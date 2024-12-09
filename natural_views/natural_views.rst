.. _natural_views:

Natural Views
=============

.. image:: /images/nat_view.png

With natural views, we exploit the SQL view concept and map high naturalness identifiers to their native (possibly lower naturalness) representations.

This pipeline requires the :ref:`snails_naturalness_classifier`, :ref:`schemarenamer`, and :ref:`natural_view_builder` modules.

The `Schema classification/modification, and view creation <https://github.com/KyleLuoma/SNAILS/blob/main/classify_rename_and_build_view.py>`_ script
is an end-to-end example of how to use SNAILS artifacts to improve database naturalness.

.. toctree::
    :maxdepth: 2
    :caption: Contents: