Welcome to MetQuest's documentation!
====================================

MetQuest is a dynamic programming based algorithm for identifying all possible
pathways from metabolic networks between the source and the target metabolites. 
MetQuest requires the genome-scale metabolic reconstructions,
set of seed, source and target metabolites and the pathway length cut-off. 
MetQuest is compatible with Python 3 and is OS-independent.  

Authors
=======

-  `Aarthi Ravikrishnan <https://github.com/aarthi31>`__
-  Meghana Nasre
-  `Karthik Raman <https://github.com/karthikraman>`__


License
=======

1. By using the software enclosed in this package (MetQuest), you agree to become bound by the terms of this license. 
2. This software is for your internal use only. Please DO NOT redistribute it without the permission from the authors.
3. This software is for **academic use only**. No other usage is allowed without a written permission from the authors. It cannot be used for any commercial interest.
4. The authors appreciate it if you can send us your feedback including any bug report.
5. The authors do not hold any responsibility for the correctness of this software, though we cross-checked all experimental results.


Acknowledgments
===============
This work was supported by the Indian Institute of Technology Madras grant ERP/1314/004/RESF/KARH to KR and the INSPIRE fellowship, Department of Science and Technology, Government of India to AR.


************
Installation
************

Use pip3 to install metquest from `PyPI: <https://pypi.python.org/pypi/metquest>`__

Via Python Package
==================

.. code:: bash

    pip3 install metquest


Direct installation
===================

1. Install `Python 3.4 or higher <https://www.python.org/downloads/>`__
2. Clone this repository to your computer using ``git`` or `download the
   repository <https://github.com/aarthi31/MetQuest/>`__ and decompress
   it. 
3. Navigate to the folder where metquest is downloaded and type

.. code:: bash

    python3 setup.py install

(Elevated ``sudo`` rights may be required depending on the platform)


Required python packages
========================
1. cobra >= 0.11.3
2. numpy >= 1.14.3
3. scipy
4. python-libsbml
5. networkx >= 2.1

Input
=====

Folder whose structure is as shown:

.. code-block:: text

    mainfolder/
    |-Example1/
    |   |-- SBML model(s) of metabolic networks # XML files of the metabolic networks(COBRA-compatible)
    |   |-- seed_mets.txt       # Text file containing the seed metabolites separated by a newline
    |   │-- source_mets.txt     # Text file containing the source metabolites separated by a newline
    |   |-- target_mets.txt     # Text file containing the target metabolites separated by a newline
    |   |-- cutoff.txt          # Text file containing the size cut-offs separated by a newline  
    |-Example2/
    |   ...

Kindly ensure that the SBML model has the field <model id> and the metabolites
are prefixed with the model identifiers, for instance, if the model identifier is 
'ecoli_core_model', and the seed metabolite is 'fum_c', the input text file
should contain ecoli_core_model fum_c

Running MetQuest
================

From command line
*****************
MetQuest can be directly run from the terminal as

.. code:: bash

    metquest.sh <path containing the input folder>


Navigate to the folder where metquest is installed and type

.. code:: bash

    python3 execute_metquest.py <path containing the input folder>


From python console
********************

.. code:: python

>>> import metquest
>>> metquest.execute_all_codes()


When prompted, enter the path containing the folder with all the data files

Running examples
****************

In the python console, type the following

.. code:: python

>>> import metquest
>>> metquest.example.run_this_example()


This will run the example files.
