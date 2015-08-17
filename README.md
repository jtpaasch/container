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

Build an image called `foo` from a `Dockerfile` in the folder 
`/usr/local/workdir`:

    $ container build foo /usr/local/workdir

If the Dockerfile is in a subfolder of the build directory, specify it's 
location (relative to the build directory) with the `--dockerfile` flag. 
For instance:

    $ container build foo /usr/local/workdir --dockerfile dev/Dockerfile

The build directory is what docker calls the "build context," which means 
the image only has access to files inside the build directory, and nothing 
outside it.


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

To add the folder `/usr/share` (on your machine) to the `foo` container as `/var/share`: 

    $ container start foo --volume /usr/share:/var/share

To forward the container's port `8000` to your machine's port `8011`:

    $ container start foo --port 8011:8000

To link another container called `db`: 

    $ container start foo --link db


Listing running containers
--------------------------

To see a list of all running containers:

    $ container ps


Get a container's IP address
----------------------------

To get the IP address of the running container `foo`:

    $ container ip foo


Get detailed container info
---------------------------

To get all information about the running container `foo`:

    $ container info foo


Stopping containers
-------------------

To stop the running `foo` image:

    $ container stop foo

