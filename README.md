# CMakeLint

[![Build Status](https://travis-ci.org/cmake-lint/cmake-lint.svg?branch=develop)](https://travis-ci.org/cmake-lint/cmake-lint)
![PyPI](https://img.shields.io/pypi/v/cmakelint.svg)
![PyPI - Downloads](https://img.shields.io/pypi/dd/cmakelint.svg)
![PyPI - Downloads](https://img.shields.io/pypi/dm/cmakelint.svg)

cmakelint parses CMake files and reports style issues.

cmakelint requires Python.

## Installation

To install cpplint from PyPI, run:

.. code-block:: bash

    $ pip install cmakelint

## Usage

    Syntax: cmakelint [--config=file] [--filter=-x,+y] <file> [file] ...
    filter=-x,+y,...
      Specify a comma separated list of filters to apply

    config=file
      Use the given file for configuration. By default the file
      $HOME/.cmakelintrc is used if it exists.  Use the value "None" to use no
      configuration file (./None for a file called literally None)
      Only the option "filter=" is currently supported in this file.

Run the `--filter=` option with no filter to see available options. Currently
these are:

    convention/filename
    linelength
    package/consistency
    readability/logic
    readability/mixedcase
    readability/wonkycase
    syntax
    whitespace/eol
    whitespace/extra
    whitespace/indent
    whitespace/mismatch
    whitespace/newline
    whitespace/tabs

An example .cmakelintrc file would be as follows:

    filter=-whitespace/indent

With this file in your home directory, running these commands would have the
same effect:

    cmakelint.py CMakeLists.txt
    cmakelint.py --filter=-whitespace/indent CMakeLists.txt

# Output status codes

The program should exit with the following status codes:

* 0 if everything went fine
* 1 if an error message was issued
* 32 on usage error
