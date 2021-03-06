.. _sec-examples:

Examples
========

M-LOOP includes a series of example configuration files for each of the controllers and interfaces. The examples can be found in examples folder.  For some controllers there are two files, ones ending with *_basic_config* which includes the standard configuration options and *_complete_config* which include a comprehensive list of all the configuration options available.

The options available are also comprehensively documented in the :ref:`sec-api` as keywords for each of the classes. However, the quickest and easiest way to learn what options are available, if you are not familiar with python, is to just look at the provided examples.

Each of the example files is used when running tests of M-LOOP. So please copy and modify them elsewhere if you use them as a starting point for your configuration file. 

Interfaces
----------

There is currently one interface supported: 'file'. You can specify which interface you want with the option::

   interface_type = [name]

The default will be 'file'. The specific options for each of the interfaces are described below.

File Interface
~~~~~~~~~~~~~~

You can change the names of the files used for the file interface and their type. The file interface options are described in *file_interface_config.txt*.

.. include:: ../examples/file_interface_config.txt
   :literal:

Controllers
-----------

There are currently three controller types supported: 'gaussian_process', 'random' and 'nelder_mead'. The default is 'gaussian_process'. You can set which interface you want to use with the option::

   controller_type = [name]

Each of the controllers and their specific options are described below. There is also a set of common options shared by all controllers which is described in *controller_options.txt*. The common options include the parameter settings and the halting conditions.

.. include:: ../examples/controller_config.txt
   :literal:
   
Gaussian Process
~~~~~~~~~~~~~~~~

The Gaussian-process controller is the default controller and is the currently the most sophisticated machine learner algorithm. It uses a `Link Gaussian process <http://scikit-learn.org/dev/modules/gaussian_process.html>`_ to develop a model for how the parameters relate to the measured cost, effectively creating a model for how the experiment operates. This model is then used when picking new points to test. 

There are two example files for the Gaussian-process controller: *gaussian_process_simple_config.txt* which contains the basic options.

.. include:: ../examples/gaussian_process_simple_config.txt
   :literal:
   
*gaussian_process_complete_config.txt* which contains a comprehensive list of options.

.. include:: ../examples/gaussian_process_complete_config.txt
   :literal:
   
Nelder Mead
~~~~~~~~~~~

The Nelder Mead controller implements the `Link Nelder-Mead method <https://en.wikipedia.org/wiki/Nelder%E2%80%93Mead_method>`_ for optimization. You can control the starting point and size of the initial simplex of the method with the configuration file.

There are two example files for the Nelder-Mead controller: *nelder_mead_simple_config.txt* which contains the basic options.

.. include:: ../examples/nelder_mead_simple_config.txt
   :literal:
   
*nelder_mead_complete_config.txt* which contains a comprehensive list of options.

.. include:: ../examples/nelder_mead_complete_config.txt
   :literal:
   
Random
~~~~~~

The random optimization algorithm picks parameters randomly from a uniform distribution from within the parameter bounds or trust region. 

There are two example files for the random controller: *random_simple_config.txt* which contains the basic options.

.. include:: ../examples/random_simple_config.txt
   :literal:
   
*random_complete_config.txt* which contains a comprehensive list of options.

.. include:: ../examples/random_complete_config.txt
   :literal:
   
Logging
-------

You can control the filename of the logs and also the level which is reported to the file and the console. For more information see `Link logging levels <https://docs.python.org/3.6/library/logging.html#levels>`_. The logging options are described in *logging_config.txt*.

.. include:: ../examples/logging_config.txt
   :literal:

Extras
------

Extras refers to options related to post processing your data once the optimization is complete. Currently the only extra option is for visualizations. The extra options are described in *extras_config.txt*.

.. include:: ../examples/extras_config.txt
   :literal:


