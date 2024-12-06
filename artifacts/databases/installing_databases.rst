.. _installing_databases:

Database Installation
=====================

We offer the SNAILS database collection in both MS SQL and Sqlite formats.

To run any SNAILS reproducibility scripts, you must first download the MS SQL backup files here:

`https://drive.google.com/file/d/1EMQmdNx-a20TfZSDdNkFPLmXVS48IB2b/view?usp=drive_link <https://drive.google.com/file/d/1EMQmdNx-a20TfZSDdNkFPLmXVS48IB2b/view?usp=drive_link>`_

If you're running **Windows**, you can either use Docker or import the provided .bak files into a MS SQL server database
`following the steps here <https://learn.microsoft.com/en-us/sql/relational-databases/backup-restore/quickstart-backup-restore-database?view=sql-server-ver16&tabs=ssms>`_.

Once you've imported the .bak files into an MS SQL database, you'll need to configure the ``.local/dbinfo.json`` file for your system's login credentials. If this is too complicated, then consider using the Docker-based approach below.

For **Linux**, **WSL**, or **Apple** users, we recommend the Docker-based approach.

1. Download the ``SNAILS_database_collection.tar.gz`` from the link above into ``./SNAILS_Artifacts/databases/``
2. In the ``./SNAILS_Artifacts/databases/`` directory, Run::

    bash install_snails_db.sh
    bash run_docker_snails_db.sh

This will build a MS SQL docker image, copy the .bak files into the container, and unzip and import the .bak files into the database. It will also copy the required ``dbinfo.json`` file into the ``./.local/`` directory.


**SNAILS SQlite** is required for reproducing CodeS-based inference.

`Download the collection <https://drive.google.com/file/d/16vgE_KCZMdKDKHtXgIQhvWdwO7ufKcjz/view?usp=drive_link>`_ and unzip into the ``./db/snails_sqlite/`` directory.


.. toctree::
    :maxdepth: 2
    :caption: Contents:
