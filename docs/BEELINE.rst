.. _beeline:
   

BEELINE
=======

Overview
--------

BEELINE provides a set of tools for evaluating methods that infer gene
regulatory networks (GRN) from single-cell gene expression
data. The BEELINE framework is divided into the following modules:

* :ref:`blrun` : contains the BEELINE's Runner module, a Python
  wrapper for 12 GRN inference algorithms with options to add new
  methods.
* :ref:`bleval` : contains the BEELINE's Evaluation module that
  provides easy-to-use tools for evaluating GRN reconstructions.
* :ref:`blplot` : contains the BEELINE's plotting module for
  visualizing output from BLEval.



Getting Started
---------------

The BEELINE pipeline interfaces with the implementations of various
algorithms through Docker containers.  Please follow this tutorial on
how to `install docker
<https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-18-04>`_
on Ubuntu 18.0.



.. tip:: Setup docker to run docker without sudo using the following shell command

   .. code:: sh

                   sudo usermod -aG docker $USER

   See more details `here <https://askubuntu.com/questions/477551/how-can-i-use-docker-without-sudo>`_.

Once docker has been set up correctly, the next step is to create the
docker containers for each of the algorithms.  The script
`initialize.sh` builds these containers. Run the following in the
terminal

.. code:: bash

          . initialize.sh
          
.. note:: This step will take a while!

   
To compute ranked list of edges, run

.. code:: python

          python BLRun.py --config config-files/config.yaml
    
To compute areas under the ROC and PR curves using the BEELINE's
evaluation pipeline, run

.. code:: bash

          python BLEvalAggregator.py --config config-files/config.yaml --auc

To display the complete list of
evaluation options, run

.. code:: bash
          
          python BLEvalAggregator.py --help

Tutorial
--------

.. include:: beeline-tutorial.rst
             
.. _algorithms:

Details of supported algorithms 
-------------------------------

.. include:: algorithms.rst

             
Developer Guide
---------------

.. include:: beeline-developer.rst

             
API Reference
-------------

.. include:: beeline-reference.rst


