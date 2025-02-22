==========
User guide
==========


***************
Access AiiDAlab
***************

As a user, you have three options to access AiiDAlab:

 1. Log into one of the `open AiiDAlab servers <https://materialscloud.org/aiidalab>`_.
 2. Download the `Quantum Mobile Virtual Machine <https://quantum-mobile.readthedocs.io/>`_, open a terminal and run ``aiidalab``.
 3. Run the AiiDAlab docker container on your local machine (see below).

.. _usage:run-locally:

Run AiiDAlab locally
====================

Prerequisites
-------------

Linux or MacOS with `Docker installed <https://www.docker.com/get-started>`__


Instructions
------------

Pull the AiiDAlab docker image from DockerHub and tag it so that the startup script recognizes it:

   .. code-block:: console

       $ docker pull aiidalab/aiidalab-docker-stack:latest
       $ docker tag aiidalab/aiidalab-docker-stack:latest aiidalab-docker-stack:develop

Clone the `AiiDAlab Docker Stack <https://github.com/aiidalab/aiidalab-docker-stack>`__ repository and enter the cloned directory:

   .. code-block:: console

       $ git clone https://github.com/aiidalab/aiidalab-docker-stack
       $ cd aiidalab-docker-stack

Start AiiDAlab by running:

   .. code-block:: console

       $ ./run.sh --no-build 8888 ~/aiidalab


  * ``8888`` is the port under which the AiiDAlab web interface will be available.
  * ``~/aiidalab`` is the **absolute** path to the directory that will be mounted as the persistent home directory inside the container.
    If the directory does not exist, it will be created.

The startup procedure can take a while, particularly when you run it for the first time.
Once it is done, open the link provided at the bottom of the console in your web browser.
You should now see the AiiDAlab home page.

.. note::

    The instructions above use the pre-built AiiDAlab docker image from DockerHub.
    In order to build the image yourself (e.g. to apply modifications), simply run the script without the ``--no-build`` option::

        ./run.sh 8888 ~/aiidalab


******************
AiiDAlab Home page
******************

When opening AiiDAlab you see a list of installed applications.
The front page is generated by the AiiDAlab home app which cannot be uninstalled.
Its main features are:

- **File manager**: manage files stored in the AiiDAlab home folder (including download/upload).
- **Terminal**: a standard Linux bash terminal.
- **Tasks**: view the currently running applications and stop them, if needed.
- **App Store**: install/remove applications.
- **Help**: links to the AiiDAlab documentation.


****************************
Install/update/delete an app
****************************

[Related issue: `#152 <https://github.com/aiidalab/aiidalab/issues/152>`_]
