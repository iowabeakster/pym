

==========
Virtualenv
==========

Virtual Python Environment builder or virtualenv is a tool which will help you to install different versions of python modules in a local directory using which you can develop and test your code without requiring to install everything systemwide.

Installation
============

You can install virtualenv ewither from distro provided package or through pip.

::

    $ sudo yum install python-virtualenv

Or

::

    $ sudo pip install virtualenv

Usage
=====

We will create a directory call *virtual* inside which we will have two different virtual environment.

The following commands will the create an env called virt1.

::

    $ cd virtual
    $ virtualenv virt1 
    New python executable in virt1/bin/python
    Installing setuptools............done.
    Installing pip...............done.

Now we can virt1 environment.

::

    $ source virt1/bin/activate
    (virt1)[user@host]$

The firt part of the prompt is now name of the virtual environment, it will help you to understand which environment you are in when you will have many environments.

To deactivate the environment use *deactivate* command.

::

    (virt1)$ deactivate
    $

So, now we will install a python module called redis.

::

    (virt1)$ pip install redis
    Downloading/unpacking redis
    Downloading redis-2.6.2.tar.gz
    Running setup.py egg_info for package redis
    Installing collected packages: redis
    Running setup.py install for redis
    Successfully installed redis
    Cleaning up...

Same way we can install a project called yolk, which can tell us which all modules are installed.

::

    (virt1)$ pip install yolk
    (virt1)$ yolk -l
    Python          - 2.7.3        - active development (/usr/lib64/python2.7/lib-dynload)
    pip             - 1.1          - active
    redis           - 2.6.2        - active
    setuptools      - 0.6c11       - active
    wsgiref         - 0.1.2        - active development (/usr/lib64/python2.7)
    yolk            - 0.4.3        - active

Now we will create another virtual environment *virt2* where we will install same redis module but an old 2.4 version.

::

    $ virtualenv virt2
    New python executable in virt1/bin/python
    Installing setuptools............done.
    Installing pip...............done.
    $ source virt2/bin/activate
    (virt2)$
    (virt2)$ pip install redis==2.4
    Downloading/unpacking redis
    Downloading redis-2.4.0.tar.gz
    Running setup.py egg_info for package redis
    Installing collected packages: redis
    Running setup.py install for redis
    Successfully installed redis
    Cleaning up...
    (virt1)$ pip install yolk
    (virt1)$ yolk -l
    Python          - 2.7.3        - active development (/usr/lib64/python2.7/lib-dynload)
    pip             - 1.1          - active
    redis           - 2.4.0        - active
    setuptools      - 0.6c11       - active
    wsgiref         - 0.1.2        - active development (/usr/lib64/python2.7)
    yolk            - 0.4.3        - active

As you can see yolk says that in this envrionment we have redis 2.4 installed. This way you can have many different environments for your all development needs.

.. note:: Always remember to create virtualenvs while developing new applications. This will help you to keep the system modules clean.


