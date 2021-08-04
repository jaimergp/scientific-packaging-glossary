# Conda glossary

An overview of the conda universe and all the satellitary tools we can find out there.


### Package Managers


conda
:   A cross-platform, language-agnostic package manager created by Anaconda Inc.

mamba
:   A drop-in replacement for conda developed by QuantStack. Some parts, like the solver, were rewritten in C++ for pefromance.

micromamba
:   A full C++ rewrite of most parts of the conda package manager, also developed by QuantStack. It does not require a Python installation.

pip
:   PyPA's de facto Python package manager.

### Workflows


poetry
:   Poetry helps you declare, manage and install dependencies of Python projects, ensuring you have the right stack everywhere.

flit
:   Flit is a simple way to put Python packages and modules on PyPI. It tries to require less thought about packaging and help you avoid common mistakes.

conda-devenv
:   A conda tool to work with multiple projects in development mode.

pipenv
:   Pipenv harnesses Pipfile, pip, and virtualenv into one single command.

### Conda Package Builders


conda-build
:   The de facto tool to create conda packages. It creates environments to isolate build-times dependencies and performs checks after compilation to ensure relocatability and correct runtime dependencies.

boa
:   Boa does to conda-build what Mamba did for conda-install: it replaces slow parts with C++ code to improve performance and debuggability.

mambabuild
:   A drop-in replacement for conda-build provided by Boa. It relies on conda-build for most parts, but replaces the solver and the error reports. It provides the 'conda mambabuild' command.

### Wheel Builders


meson
:   Meson is an open source build system meant to be both extremely fast, and, even more importantly, as user friendly as possible. It can produce Python wheels through the mesonpep517 package.

mesonpep517
:   A simple module that implements PEP517 for the meson build system.

pypa/build
:   It invokes the PEP 517 hooks to build a distribution package. It is a simple build tool and does not perform any dependency management.

scikit-build
:   Improved build system generator for CPython C/C++/Fortran/Cython extensions. The scikit-build package is fundamentally just glue between the setuptools Python module and CMake.

setuptools
:   Setuptools is a collection of enhancements to the Python distutils library to easily build and distribute Python packages.

distutils
:   The distutils package in the standard library provides support for building and installing additional modules into a Python installation. Most Python users will not want to use this module directly, but enhanced alternatives like setuptools.

numpy.distutils
:   This Numpy subpackage provides enhanced distutils functionality to make it easier to build and install sub-packages, auto-generate code, and extension modules that use Fortran-compiled libraries.


### Bundlers / Installer Creation / Redistribution


constructor
:   Constructor is a tool which allows constructing an installer for a collection of conda packages. It solves needed packages using user-provided specifications, and bundles those packages.

pex
:   pex is a library for generating .pex (Python EXecutable) files which are executable Python environments in the spirit of virtualenvs. pex is an expansion upon the ideas outlined in PEP 441.

shiv
:   shiv is a command line utility for building fully self contained Python zipapps as outlined in PEP 441, but with all their dependencies included.

pyinstaller
:   PyInstaller freezes (packages) Python applications into stand-alone executables, under Windows, GNU/Linux, Mac OS X, FreeBSD, Solaris and AIX.

conda-pack
:   conda-pack is a command line tool for creating relocatable archives of conda environments that can be installed on other systems and locations.

conda-docker
:   Create minimal Docker images from conda environments, without using Docker.

conda-store
:   The core philosophy of conda-store is to serve identical conda environments in as many ways as possible. Conda Store controls the environment lifecycle: management, builds, and serving of environments.

### Package Publishing


anaconda-client
:   This is a command line client that provides an interface to Anaconda Cloud. Primarily used to upload packages to Anaconda.org channels.

twine
:   A utility for publishing Python packages on PyPI. It provides build system independent uploads of source and binary distribution artifacts for both new and existing projects.

zest.releaser
:   zest.releaser is collection of command-line programs to help you automate the task of releasing a Python project. It updates the version number, populates the changelog, creates the tags and, optionally, publishes to PyPI.

### CI / Infrastructure Tooling


conda-smithy
:   conda-smithy is a tool for combining a conda recipe with configurations to build using freely hosted CI services into a single repository, also known as a feedstock.

conda-forge-ci-setup
:   A package installed by conda-forge each time a build is run on CI. It normalizes the system settings found on different CI providers for a consistent build configuration across platforms.

conda-forge-pinning
:   The baseline versions of software for the conda-forge ecosystem, essential to maintain ABI compatibility across the channel.

cibuildwheel
:   Build Python wheels for all the platforms on CI with minimal configuration.

multibuild
:   Machinery for building and testing Python Wheels for Linux, OSX and (less flexibly) Windows.

### Package Conversion


conda-skeleton
:   The conda-skeleton command picks up the PyPI package metadata and prepares an equivalent conda-build recipe you can use to build a conda package.

conda_package_handling
:   Create, extract and convert conda packages of various formats.

grayskull
:   The Grayskull project was created with the intention to eventually replace the conda skeleton. The main goal of this project is to generate concise recipes for conda-forge.

conda-press
:   Press conda packages into wheels. Is allows us to build out a pip-usable package index which is ABI compatible with conda packages.

### Package Validation / Mangling / Signing


conda-verify
:   conda-verify is a tool for (passively) verifying conda recipes and conda packages. The purpose of this verification process is to ensure that recipes don't contain obvious bugs.

conda-content-trust
:   Signing and verification tools for Conda based on The Update Framework

auditwheel
:   a command line tool to facilitate the creation of Python wheel packages for Linux (containing pre-compiled binary extensions) that are compatible with a wide variety of Linux distributions

pip-check
:   Verify installed packages have compatible dependencies.

delocate
:   Find and copy needed dynamic libraries into python wheels

check-wheel-contents
:   Check the contents of your wheel. It will notify you of several common errors & mistakes that can be detected.

machomachomangler
:   This is a little library for mangling Mach-O and PE files in various ways. These are the formats used for executables and shared libraries on MacOS and Windows, respectively.

patchelf
:   A small utility to modify the dynamic linker and RPATH of ELF executables.

lief
:   The purpose of this project is to provide a cross platform library which can parse, modify and abstract ELF, PE and MachO formats.

### Virtual Environments


virtualenv
:   virtualenv is a tool to create isolated Python environments. Since Python 3.3, a subset of it has been integrated into the standard library under the venv module.

venv
:   The venv module in the standard library provides support for creating lightweight virtual environments with their own site directories, optionally isolated from system site directories.

virtualenvwrapper
:   virtualenvwrapper is a set of extensions to Ian Bicking’s virtualenv tool. The extensions include wrappers for creating and deleting virtual environments and otherwise managing your development workflow,

conda-env
:   Conda/Mamba/Micromamba are able to handle their own virtual environments through 'conda env'. They are not compatible with virtualenv-type environments, but they serve the same purpose.

### Index Serving


conda-index
:   Update package index metadata files (channeldata.json, repodata.json) in directories containing conda packages.

conda-mirror
:   Mirrors an upstream conda channel to a local directory.

quetz
:   The quetz project is an open source server for conda packages. It reimplements Anaconda.org functionalities with an API-first approach.

warehouse
:   Warehouse is the software that powers PyPI.

devpi
:   Python PyPi staging server and packaging, testing, release tool

pypiserver
:   pypiserver is a minimal PyPI compatible server for pip or easy_install. It is based on bottle and serves packages from regular directories.

### Build Instructions


meta.yaml
:   All the metadata in the conda-build recipe is specified in the meta.yaml file. It contains info such as the package name, version, source URL, build dependencies, runtime requirements, tests and licensing. It supports Jinja and platform selectors.

conda_build_config.yaml
:   Conda build can produce variants of the same package (e.g. different Python versions). This file controls the variables injected to meta.yaml. This is the main mechanism behind 'conda-forge-pinning'.

setup.py
:   Distutils/setuptools script that provides a function to install a Python package with or without compiled extensions.

setup.cfg
:   Accompanying metadata file for setup.py that defines some configuration parameters.

pyproject.toml
:   Static file that provides all the information necessary to create an installable Python package. This alleviates the main problem of setup.py: its contents are dynamic and need to be executed to get retrieved.

### Install Instructions


environment.yaml
:   A file specifying conda packages and what channels to get them from. Users can also add pip packages here. It can be ingested by conda/mamba env and micromamba create. The tool will solve the environment and install the required packages.

conda.lock
:   Contains the definitions of an already solved conda environment. It can be generated by conda-lock, and consumed by conda install -f.

poetry.lock
:   Similar to conda-lock, Poetry can freeze an existing virtual environment, writing the exact package definitions to this file.

Pipfile.lock
:   When Pipfile or pipenv create an environment, it can be frozen to exact specifications into this file.

requirements.txt
:   A file containing a list of packages (and some command line options) to be installed by pip.

repodata.json
:   Conda channels store package metadata for each architecture (linux-64, win-64, etc) in these JSON files. Each package reports here which package they depend on, among other things.

current_repodata.json
:   Stripped down repodata.json which only contains the last build of each package, plus their dependencies, recursively. It simplifies the solver stage in some cases.

channeldata.json
:   A channel-wide metadata file that contains an index of all the conda packages present across all architectures in the channel.

### Package Formats


.tar.bz2
:   Conda packages are distributed as bzip2-compressed tarballs, including the package files and some metadata.

.conda
:   The new generation format for conda packages separates metadata from package files for quicker access. Still under deployment.


sdist
:   A source code distribution available in PyPI. Pip will prefer wheels by default.

wheel
:   Platform-specific build of a PypI package that can contain compiled libraries. Pip will prefer this if a sdist is present.

### Specs


CFEP
:   Conda Forge Enhancement Proposal. A document that formalizes a request for comments or changes in the conda-forge community.

CEP
:   Conda Enhancement Proposal. A document that formalizes a request for comments or changes in the conda tooling managed by Anaconda.

PEP
:   Python Enhancement Proposal. A document that formalizes a request for comments or changes in the Python language and its governance.

PEP440
:   This PEP describes a scheme for identifying versions of Python software distributions, and declaring dependencies on particular versions.

PEP621
:   This PEP specifies how to write a project's core metadata in a pyproject.toml file for packaging-related tools to consume.

PEP517
:   This PEP formalizes a build-system independent format for source trees. Tightly linked to PEP518.

PEP518
:   This PEP specifies how Python software packages should specify what build dependencies they have in order to execute their chosen build system. See PEP517 too.

### Installer Provision


ensurepip
:   The ensurepip standard library package provides support for bootstrapping the pip installer into an existing Python installation or virtual environment.

ensureconda
:   Ensureconda is a CLI tool that will find a preexisting conda/mamba executable, install one if none was found, and return the path of the found/installed location.

condacolab
:   A Python package to install Conda (and friends) on live Google Colab instances.

setup-miniconda
:   An action to enable the preinstalled Miniconda or download and install Miniconda/Miniforge/Mambaforge on Github Actions workflows.

provision-with-micromamba
:   A GitHub Actions action to create conda environments with micromamba.

### Python Distributions


Miniconda
:   A Python installation plus the conda package manager, packaged by Anaconda Inc.

Miniforge
:   Same as Miniconda, but preconfigured for conda-forge.

Mambaforge
:   Same as Miniforge, but including the Mamba package manager.

### Organizations


Anaconda
:   The company behind conda, the package manager. Formerly Continuum Analytics. This is also a common way to refer to the Anaconda Individual Edition, a Python distribution that contains hundreds of ready to use data science packages plus the conda package manager.

conda-forge
:   A community-led collection of recipes, build infrastructure and distributions for the conda package manager.

bioconda
:   Bioconda is a channel for the conda package manager specializing in bioinformatics software.

QuantStack
:   QuantStack is the company in charge of developing Mamba, Micromamba, Boa and Quetz.

conda-incubator
:   A Github organization that hosts community-developed tools in the conda ecosystem.

conda-tools
:   Another Github organization that hosts community-developed tools in the conda ecosystem, tightly linked to conda-forge.

mamba-org
:   The GitHub organization that hosts QuantStack's open-source conda reimplementations Mamba, Boa and Quetz.

PyPA
:   The Python Packaging Authority, which governs PyPA, pip and other Python-first packaging tooling and services.

PSF
:   The Python Software Foundation.

### Concepts


defaults
:   The set of channels preconfigured in the Anaconda / Miniconda distributions. In short, packages built and distributed by Anaconda Inc.

metapackage
:   A package that does not distribute files. It only specifies dependencies on other actual packages.

virtual-package
:   In conda speech, a metadata-only package exposed by the conda tooling to express hardware features as package constraints (e.g. supported CUDA versions). They always start with a double underscore.

virtual-environment
:   An isolated Python installation that can coexist along other installations. They are usually activated on-demand whenever they are needed.

### Package Repositories


anaconda.org
:   The authoritary source for conda packages. It consists of several channels, including defaults, conda-forge, bioconda and thousands more.

PyPI
:   The Python Package Index. The main source for wheels and sdists. This is where pip usually downloads files from.