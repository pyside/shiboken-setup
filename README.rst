========
Shiboken
========

.. contents:: **Table of Contents** 

Introduction
============

Shiboken generates bindings for C++ libraries using CPython source code.

Installation
============

Installing prerequisities
-------------------------

Install latest `pip` distribution: download `get-pip.py
<https://raw.github.com/pypa/pip/master/contrib/get-pip.py>`_ and run it using
the ``python`` interpreter.

Installing Shiboken on a Windows System
---------------------------------------

To install Shiboken on Windows you can choose from the following options:

#. Use pip to install the `wheel` binary packages:
   
   ::

      pip install --use-wheel -U Shiboken

#. Use setuptools to install the `egg` binary packages:
   
   ::

      easy_install -U Shiboken

Installing Shiboken on a UNIX System
------------------------------------

We do not provide binaries for UNIX System. Please read the build instructions in section
``Building Shiboken on a UNIX System``.

Building Shiboken on a Windows System
=====================================

Installing prerequisities
-------------------------

#. Install `Python
   <http://www.python.org/download/>`_.

#. Install `Qt 4.8 libraries for Windows VS 2008 edition
   <http://download.qt-project.org/official_releases/qt/4.8/4.8.5/qt-win-opensource-4.8.5-vs2008.exe>`_
   when building against Python 2.6, 2.7 or 3.2.
   Install `Qt 4.8 libraries for Windows VS 2010 edition
   <http://download.qt-project.org/official_releases/qt/4.8/4.8.5/qt-win-opensource-4.8.5-vs2010.exe>`_
   when building against Python 3.3 or 3.4.

#. Install `Cmake
   <http://www.cmake.org/cmake/resources/software.html>`_.

#. Install `Windows SDK v7.0
   <http://www.microsoft.com/en-us/download/details.aspx?id=3138>`_
   when building against Python 2.6, 2.7 or 3.2.
   Install `Windows SDK v7.1
   <http://www.microsoft.com/en-us/download/details.aspx?id=8279>`_
   when building against Python 3.3 or 3.4.

#. Install `Git
   <http://git-scm.com/download/win>`_.

#. Install latest `pip` distribution into the Python you
   installed in the first step: download `get-pip.py 
   <https://raw.github.com/pypa/pip/master/contrib/get-pip.py>`_ and run it using
   the ``python`` interpreter of your Python 2.7 installation using a
   command prompt:

   ::

      c:\> c:\Python27\python get-pip.py

#. Install latest `wheel` distribution:

   ::

      c:\> c:\Python27\Scripts\pip install wheel

Building Shiboken distribution
------------------------------

#. Download and extract `Shiboken source distribution
   <https://pypi.python.org/packages/source/S/Shiboken/Shiboken-1.2.2.tar.gz>`_

#. Switch to the distribution directory:

   ::

      c:\> cd Shiboken-1.2.2

#. Build the `wheel` binary distribution:

   ::

      c:\> c:\Python27\python.exe setup.py bdist_wheel --qmake=c:\Qt\4.8.5\bin\qmake.exe

Building Shiboken distribution from git repository
--------------------------------------------------

#. Clone ``Shiboken`` setup scripts from git repository:

   ::

      c:\> git clone https://github.com/PySide/shiboken-setup.git shiboken-setup

#. Switch to the ``shiboken-setup`` directory:

   ::

      c:\> cd shiboken-setup

#. Build the `wheel` binary distribution:

   ::

      c:\> c:\Python27\python.exe setup.py bdist_wheel --version=1.2.2 --qmake=c:\Qt\4.8.5\bin\qmake.exe

#. To build the development version of ``Shiboken`` distribution, ignore the --version parameter:

   ::

      c:\> c:\Python27\python.exe setup.py bdist_wheel --qmake=c:\Qt\4.8.5\bin\qmake.exe

Installing Shiboken distribution
--------------------------------

#. After the successful build, install the distribution with ``pip``:
   
   ::

      c:\> c:\Python27\Scripts\pip install --use-wheel dist\Shiboken-1.2.2-cp27-none-win32.whl

Installing Shiboken distribution into ``virtual`` Python environment
--------------------------------------------------------------------

#. Install latest `virtualenv` distribution:

   ::

      c:\> c:\Python27\Scripts\pip install virtualenv

#. Use `virtualenv` to make a workspace:

   ::

      c:\> c:\Python27\Scripts\virtualenv --no-site-packages env

#. Switch to the ``env`` directory:

   ::

      c:\> cd env

#. Install the distribution with ``pip``:
   
   ::

      c:\> Scripts\pip install ..\dist\Shiboken-1.2.2-cp27-none-win32.whl

Building Shiboken on a UNIX System (Ubuntu 12.04 - 14.04)
=========================================================

Installing prerequisities
-------------------------

#. Install build dependencies:

   ::

      $ sudo apt-get install build-essential git cmake libqt4-dev python2.7-dev libxml2-dev libxslt1-dev

#. Install latest `pip` distribution into the Python you
   installed in the first step: download `get-pip.py 
   <https://raw.github.com/pypa/pip/master/contrib/get-pip.py>`_ and run it using
   the ``python`` interpreter of your Python 2.7 installation using a
   command prompt:

   ::

      $ wget https://raw.github.com/pypa/pip/master/contrib/get-pip.py
      $ sudo python2.7 get-pip.py

#. Install latest `wheel` distribution:

   ::

      $ sudo pip2.7 install wheel

Building Shiboken distribution
------------------------------

#. Download ``Shiboken`` source distribution:

   ::

      $ wget https://pypi.python.org/packages/source/S/Shiboken/Shiboken-1.2.2.tar.gz

#. Extract the source distribution:

   ::

      $ tar -xvzf Shiboken-1.2.2.tar.gz

#. Switch to the distribution directory:

   ::

      $ cd Shiboken-1.2.2

#. Build the `wheel` binary distribution:

   ::

      $ python2.7 setup.py bdist_wheel --qmake=/usr/bin/qmake-qt4

#. Optionally you can build standalone version of distribution with embedded Qt libs:

   ::

      $ python2.7 setup.py bdist_wheel --qmake=/usr/bin/qmake-qt4 --standalone

Building Shiboken distribution from git repository
--------------------------------------------------

#. Clone ``Shiboken`` setup scripts from git repository:

   ::

      $ git clone https://github.com/PySide/shiboken-setup.git shiboken-setup

#. Switch to the ``shiboken-setup`` directory:

   ::

      $ cd shiboken-setup

#. Build ``Shiboken`` distribution:

   ::

      $ python2.7 setup.py bdist_wheel --qmake=/usr/bin/qmake-qt4 --version=1.2.2

#. Optionally you can build standalone version of distribution with embedded Qt libs:

   ::

      $ python2.7 setup.py bdist_wheel --qmake=/usr/bin/qmake-qt4 --version=1.2.2 --standalone

#. To build the development version of ``Shiboken`` distribution, ignore the --version parameter:

   ::

      $ python2.7 setup.py bdist_wheel --qmake=/usr/bin/qmake-qt4

Installing Shiboken distribution
--------------------------------

#. After the successful build, install the distribution with ``pip``:
   
   ::

      $ sudo pip2.7 install dist/Shiboken-1.2.2-cp27-none-linux-x86_64.whl

#. Run the post-install script to finish the package configuration:
   
   ::

      $ sudo python2.7 shiboken_postinstall.py -install

Installing Shiboken distribution into ``virtual`` Python environment
--------------------------------------------------------------------

#. Install latest `virtualenv` distribution:

   ::

      $ sudo pip2.7 virtualenv

#. Use `virtualenv` to make a workspace:

   ::

      $ virtualenv-2.7 --no-site-packages env

#. Switch to the ``env`` directory:

   ::

      $ cd env

#. Install the distribution with ``pip``:
   
   ::

      $ bin/pip2.7 install ../dist/Shiboken-1.2.2-cp27-none-linux-x86_64.whl

#. Run the post-install script to finish the package configuration:
   
   ::

      $ bin/python bin/shiboken_postinstall.py -install

Shiboken Setup Script command line options
==========================================

Usage on Windows System
-----------------------
    
   ::

      c:\> c:\Python27\python.exe setup.py [distribution_type] [options]

Usage on UNIX System
--------------------
    
   ::

      python2.7 setup.py [distribution_type] [options]

Distribution types
------------------

``bdist_wheel``
    Create wheel binary distribution.
    This distribution type can be installed with ``pip``.

``bdist_egg``
    Create egg binary distribution.
    This distribution type can be installed with ``easy_install``.

``bdist_wininst``
    Create standalone windows installer with embedded Qt libs and development tools.
    This distribution type can be installed with ``easy_install``.

``install``
    Install package to site packages folder.

``develop``
    Install package in ``development mode``, such that it's available on
    ``sys.path``, yet can still be edited directly from its source folder.

``sdist``
    Create full source distribution with included sources of Shiboken Setup Scripts
    and Shiboken. Can be used to build binary distribution in offline mode.

Options
-------

``--qmake``
    Specify the path to qmake.
    Useful when the qmake is not in path or more than one Qt versions are installed.

``--only-package``
    Skip rebuilding everything and create distribution from prebuilt binaries.
    Before using this option first time, the full distribution build is required.

``--cmake``
    Specify the path to cmake.
    Useful when the cmake is not in path.

``--standalone``
    When enabled, all required Qt libs will be included in Shiboken distribution.
    This option is allways enabled on Windows System.
    On Linux it's disabled by default.

``--version``
    Specify what version of Shiboken distribution to build.
    This option is available only when the setup scripts are cloned from git repository.

``--list-versions``
    List available versions of Shiboken distributions.

``--ignore-git``
    Don't pull sources from git repository.

``--make-spec``
    Specify the cmake makefile generator type.
    Available values are ``msvc`` on Windows System and ``make`` on UNIX System.

``--jobs``
    Specify the number of parallel build jobs

``--jom``
    Use `jom <http://qt-project.org/wiki/jom>`_ instead of nmake with msvc

``--build-tests``
    Enable building the tests

Feedback and getting involved
=============================

- Mailing list: http://lists.qt-project.org/mailman/listinfo/pyside
- Issue tracker: https://bugreports.qt-project.org/browse/PYSIDE
- Code Repository: http://qt.gitorious.org/pyside
