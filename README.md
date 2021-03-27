# atom-config<!-- TABLE OF CONTENTS -->

This repository contains the configuration file of my personal atom instance.

In the following the general setup as well as all installed packages are documented.


## Installed (community) packages

* hydrogen
* file-icons
* platformio-ide-terminal
* atom-clock
* delete-whitelines
* minimap
* minimap-highlight-selected
* script
* language-sage
* autocomplete-python
* python-autopep8
* preview-inline
* tikz-preview


## What is configured?

 * Tab length of 4 (since we are using python / sage)
 * Show indent guide (gives some indicator for indents)

I have increased the font size a little bit and the line height since I'm sitting far away (or I'm getting old).

 * Increased UI Font Size to 16 and Editor Font size to 18
 * Line height 1.75


## Installation

Notice first, that this guide was tested on MacOS. The process might be different for your system. It is also assumed that python3 and sage is already installed.

  1. Clone the repo
  ```sh
  git clone https://github.com/pgrepds/atom-config.git
  ```
  2. Place the config.cson file in ~/.atom/ (this path might depend on your operation system and the way you have installed atom)
  3. Restore installed packages from package.list via
  ```sh
  apm install --packages-file ~/.atom/package.list
  ```
  4. Check available Jupyter kernels
  ```sh
  jupyter-kernelspec list
  ```
  5. If this list is missing python3 and sage, do the following steps
  6. Install python3 ipykernel
  ```sh
  python3 -m pip install ipykernel
  python3 -m ipykernel install
  ```
  7. Identify the location of your sage installation (SAGE_ROOT) by starting sage via command line and execute
  ```sh
  SAGE_ROOT
  ```
  8. Execute the following
  ```sh
  jupyter kernelspec install --user /path/to/SAGE_ROOT
  ```
  9. Verify result by
  ```sh
  jupyter-kernelspec list
  ```
  which should yield to
  ```sh
  Available kernels:
  sagemath    /Users/david/Library/Jupyter/kernels/sagemath
  python3     /usr/local/share/jupyter/kernels/python3
  ```
  10. Start Atom in the desired working directory via
  ```sh
  atom .
  ```

## Usage

 * Run code via script package with cmd + i (be sure you have set the right file extension or choose the correct format in the bottom right corner)
 * Run code inline (individual number of lines of code) via hydrogen by selecting the lines you want to run and press (shift + enter) which results in a Jupyter Notebook like environment

 We can use inline Markdown with MathJax support. Use folding to hide actual markdown text.

<!-- LICENSE -->
## License

Distributed under the WTFPL License. See `LICENSE` for more information.
