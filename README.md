CONTAINER
=========

Build and run docker containers. Just a simple bash script to make it 
a little bit easier and quicker to build images and run them.


Requirements
------------

* OS 10.11
* `docker`, or at least something that proxies `docker` commands, 
  e.g., `boot2docker` or [`dock`](https://github.com/jtpaasch/dock).


Installation
------------

Clone or download the repo and then install the `container` script:

    $ sudo install container /usr/local/bin

See the help:

    $ container --help


Building images
---------------

Build an image called `foo` from a `Dockerfile` in the folder `/usr/local/workdir`:

    $ container build foo --build-dir /usr/local/workdir

If the Dockerfile is in a subfolder of the `build-dir`, specify it's location
(relative to the `build-dir`) with the `--dockerfile` flag. For instance:

    $ container build foo --build-dir /usr/local/workdir --dockerfile dev/Dockerfile


Listing images
--------------

See a list of all images:

    $ container list


Destroying images
-----------------

Destroy the `foo` image:

    $ container destroy foo


Running containers
------------------

Run the `foo` image:

    $ container start foo

If you want to get a bash prompt in `foo` instead, use the `--bash` flag:

    $ container start foo --bash

Listing running containers
--------------------------

To see a list of all running containers:

    $ container ps

Stopping containers
-------------------

To stop the running `foo` image:

    $ container stop `foo`



