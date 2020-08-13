# Docker Shortcuts

This repo contains bash script shortcuts for common Docker commands.  

## Usage

To use...

### Clone this repository

```
$ git clone https://github.com/elrayle/docker_shortcuts.git
```

### Add the scripts directory to your executable path

For example: Assumes that the repo was cloned to $HOME/bin

Edit $HOME/.bash_profile
```
# add docker shortcut scripts
export PATH="$HOME/bin/docker_shortcuts/scripts:${PATH}"
```

This adds the docker_shortcuts to the front of the PATH env var.  You can add it to the end if you prefer.

Execute the following to activate the change to PATH.  Need to execute in each terminal window or restart terminal.

```
$ source ~/.bash_profile
```

### List all docker shortcut commands

```
$ dhelp
``` 

## Common command combos...

### Starting composition and checking what is running

In a project where you have a docker-compose.yml, use the following to start all containers as described in the docker-compose.yml file.

```
$ dcpup
```

Check to see which images, containers, and services are loaded and running...

```
$ dls
```

Expect images to include all the images listed in the docker-compose.yml file
Expect running containers to include all containers described in the docker-compose.yml file
Expect all containers to include all loaded containers whether or not they are running.
Expect services to include all services described in the docker-compose.yml file

### Cleaning up

Starting/stopping containers and building images can create a messy environment.  If you want to start fresh, do the following to completely remove all containers and images.

***WARNING: This process gets rid of everything including running containers and images with containers.  I use it to clean up my dev machine when I want to start with a completely clean docker environment.***

#### Shut down compositions

Check which images, container, and serices are loaded and running.

```
$ dls
```

Start the cleanup by using docker-compose to clean up its images and containers.

```
$ dcpdown
```

Check which images, container, and serices are still loaded and running.

```
$ dls
```

#### Remove remaining containers

Stop all containers including running containers.

```
$ dcpruneall
```

Check all containers are stopped

```
$ dls
```

Expect the running containers and all containers lists to be empty.


#### Remove images

Remove all images without container (which should be all images at this point).

```
$ diprune
```

Check all images were removed

```
$ dls
```

Expect all lists to be empty.
