.. _installation:

Installation
============

.. contents::
    :local:
    :depth: 1

Install from Conda
------------------

.. warning::

   TODO: Prepare Conda package.

Install from GitHub
-------------------

Check out code from the esgf-wrf-lbc-extractor GitHub repo and start the installation:

.. code-block:: console

   $ git clone https://github.com/zequihg50/esgf-wrf-lbc-extractor.git
   $ cd esgf-wrf-lbc-extractor

Create Conda environment named `esgf-wrf-lbc-extractor`:

.. code-block:: console

   $ conda env create -f environment.yml
   $ source activate esgf-wrf-lbc-extractor

Install esgf-wrf-lbc-extractor app:

.. code-block:: console

  $ pip install -e .
  OR
  make install

For development you can use this command:

.. code-block:: console

  $ pip install -e .[dev]
  OR
  $ make develop

Start esgf-wrf-lbc-extractor PyWPS service
------------------------------------------

After successful installation you can start the service using the ``esgf-wrf-lbc-extractor`` command-line.

.. code-block:: console

   $ esgf-wrf-lbc-extractor --help # show help
   $ esgf-wrf-lbc-extractor start  # start service with default configuration

   OR

   $ esgf-wrf-lbc-extractor start --daemon # start service as daemon
   loading configuration
   forked process id: 42

The deployed WPS service is by default available on:

http://localhost:5000/wps?service=WPS&version=1.0.0&request=GetCapabilities.

.. NOTE:: Remember the process ID (PID) so you can stop the service with ``kill PID``.

You can find which process uses a given port using the following command (here for port 5000):

.. code-block:: console

   $ netstat -nlp | grep :5000


Check the log files for errors:

.. code-block:: console

   $ tail -f  pywps.log

... or do it the lazy way
+++++++++++++++++++++++++

You can also use the ``Makefile`` to start and stop the service:

.. code-block:: console

  $ make start
  $ make status
  $ tail -f pywps.log
  $ make stop


Run esgf-wrf-lbc-extractor as Docker container
----------------------------------------------

You can also run esgf-wrf-lbc-extractor as a Docker container.

.. warning::

  TODO: Describe Docker container support.

Use Ansible to deploy esgf-wrf-lbc-extractor on your System
-----------------------------------------------------------

Use the `Ansible playbook`_ for PyWPS to deploy esgf-wrf-lbc-extractor on your system.


.. _Ansible playbook: http://ansible-wps-playbook.readthedocs.io/en/latest/index.html
