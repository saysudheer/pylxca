<p align="center"><a href="https://www3.lenovo.com/us/en/data-center/software/systems-management/xclarity/" target="_blank" rel="noopener noreferrer"><img width="200" src="https://www3.lenovo.com/medias/lenovo-systems-software-management-xclarity-intro.png?context=bWFzdGVyfHJvb3R8NjY0OXxpbWFnZS9wbmd8aDI2L2hlMS85NDQ4OTkwODAxOTUwLnBuZ3xjZTdiOWJhNDViMTVhMjJjNTFiMWRmNzlhMDFkYzRmN2NkNGJjMzk1NTUxN2ZhYjExYWU1MDJlYmUyNGJkYjIw" alt="Lenovo Xclarity Logo"></a></p>

Python xClarity Client
===

[![Build Status](https://travis-ci.org/lenovo/xclarity_client.svg)](https://travis-ci.org/lenovo/pylxca)


What is PyLXCA?
---------------
PyLXCA is Python based interface for Lenovo xClarity Administration APIs.

PyLXCA command-line interface (CLI) provides a Python-based library of 
commands to automate provisioning and resource management.

The Lenovo XClarity Administrator PYLXCA CLI provide an interface to 
Lenovo XClarity Administrator REST APIs to automate functions such as:
*	Logging in to Lenovo XClarity Administrator
*	Managing and unmanaging chassis, servers, storage systems, and 
    top-of-rack switches (endpoints)
*	Viewing inventory data for endpoints and components
*	Deploying an operating-system image to one or more servers
*	Configuring servers through the use of Configuration Patterns
*	Applying firmware updates to endpoints


Installation
------------
To use the PYLXCA command-line interface (CLI), you must install the 
CLI and start a command session.

Python (including the request and logging modules) is required to use
to the PYLXCA CLI. Ensure at the following requirements are met. For 
more information about Python, see the [Link]www.python.org website. 

*	Python v2.7.x / Python v3.6.x
*	Python requests v2.7.0 or later
*	Python logging v0.4.9.6 or later

Complete the following steps to install the PYLXCA CLI.

1.	Download the toolkit.
2.	Unzip the package into a local directory.
3.	To install the PyLXCA frm internet, run the following command:
	
	pip install pylxca
	
	To build and install from source, download the PyLXCA source code from Python LXCA Client (PyLXCA) Toolkit website, 
	and run the following command from the source root directory:
	
	python setup.py install

4.	Start a Python shell session.

	joe@joe_vm:~# lxca_shell
	--------------------------------------------------
	Welcome to LXCA Command Shell
	Type "help" at any time for a list of commands.
	Use "lxca_shell --api" to enable Interactive Python LXCA Shell 
	--------------------------------------------------

	PyLXCA >>
	
	OR
	
	joe@joe_vm:~#lxca_shell --api
	Interactive Python Shell for Lenovo XClarity Administrator 
	Type "dir()" or "help(lxca command object)" for more information.
	>>> 
	>>> con1 = connect("https://192.0.2.0","USERID","password","True")

	Just like the Python shell, when you create the Python scripts, you can 
	use built-in Python functions in addition to PyLXCA APIs

	Note: At the beginning of your script, you must import PyLXCA and connect to the 
	Lenovo XClarity Administrator instance, for example:
	
	#!/usr/bin/env python 
	from pylxca. import *
	con1 = connect("https://192.0.2.0","USERID","password","True")

5.	Validate that the module was installed correctly by running the following command:

	In Python Shell Try to import pylxca module as follows

	>>> from pylxca. import *

	If python able to import pylxca without any error then it is installed correctly.
	
API Reference
-------------

PyLXCA command reference is available at 
http://sysmgt.lenovofiles.com/help/topic/com.lenovo.lxca.doc/pycli_overview.html?cp=1_23_1


Example
------------

python lxca_shell
connect -l https://<LXCA IPAddress> -u <LXCA User> --noverify
connect -l https://<LXCA IPAddress> -u <LXCA User>

Example to call lxca_cmd pytohn module from python script or Ansible module

from pylxca.pylxca_cmd.lxca_pyshell import *
pyshell()
con1 = connect("https://<LXCA IPAddress>",<LXCA User>,<LXCA Password>,"True")

Several sample scripts are also available to help you to quickly begin using the PYLXCA 
command-line interface (CLI) to manage endpoints. 
The sample scripts are location in the following directory:
lib/python2.7/site-packages/pylxca-1.0-py2.7.egg/pylxca\test

License
-------
Apache Software License (http://www.apache.org/licenses/LICENSE-2.0)