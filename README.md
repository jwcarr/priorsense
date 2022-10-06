priorsense
==========

Ongoing project – more details to follow.

- `code/`: Python analysis code

- `data/`: Various unprocessed and processed data files

- `experiments/`: Experimental code

- `manuscript/`: LaTeX source and postscript figures for the manuscript


Data
----

The `data` directory contains the following subdirectories: 

- `data/experiments`: Experimental parameter files and raw participant data


Analysis code
-------------

All analysis code was written for Python 3.10; it may be necessary to upgrade if you have an earlier version.

To get started, clone or download this repository and `cd` into the top-level directory:

```bash
$ cd path/to/priorsense/
```

The exact version numbers of the Python packages we used are documented in `requirements.txt`. To replicate our Python environment and ensure that the required packages do not interfere with your own projects, you will probably want to create and activate a new Python virtual environment, for example:

```bash
$ python3 -m venv priorsense_env
$ source priorsense_env/bin/activate
```

With the new environment activated, install the required Python packages from `requirements.txt`:

```bash
$ pip install --upgrade pip
$ pip install -r requirements.txt
```

If everything is installed and working correctly, the following command should give you a 👍:

```bash
$ python make_figs.py test
```

A Jupyter notebook (`notebook.ipynb`) is provided which guides you through recreating the basic results reported in the paper. If you want to dive into the data more thoroughly, I would recommend that you check the notebook first and then explore the code in the `code/` directory. To interact with the notebook, you will also need to install Jupyter Notebook:

```bash
$ pip install notebook
$ jupyter notebook
```


Experimental code
-----------------

### Experiment 1

The code for Experiment 1 is located in `experiments/exp1/`. If you just have some technical questions about the experiment, you should find answers in `main.py`.

If you actually want to run the experiment, then first note that our experiment code was written for Python 3.6 and uses the PsychoPy package. Therefore, to run this code, it is a good idea to create a separate virtual environment to create a self-contained place for all PsychoPy's dependencies, for example:

```bash
$ cd experiments/exp1/
$ python3 -m venv priorsense_env2
$ source priorsense_env2/bin/activate
$ pip install --upgrade pip
$ pip install -r requirements.txt
```

The experiment can then be run with a command like:

```bash
python main.py exp1_left 99
```

where `exp1_left` is a task ID and `99` is a participant ID. The code is intended for use with a EyeLink 1000 eye tracker and requires SR Research's Pylink Python module (n.b. this is *not* the same Pylink package on PyPI/pip) and [EyeLinkCoreGraphicsPsychoPy](https://github.com/wanjam/Easy-Eyelink-Interface); however, by default the code is in "test mode", where the mouse cursor simulates the gaze position, and can therefore be tested without any of this infrastructure in place.


License
-------

Except where otherwise noted, this repository is licensed under a Creative Commons Attribution 4.0 license. You are free to share and adapt the material for any purpose, even commercially, as long as you give appropriate credit, provide a link to the license, and indicate if changes were made. See LICENSE.md for full details.
