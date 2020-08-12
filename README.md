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

Execute the following to activate the change to PATH

```
$ source ~/.bash_profile
```

### List all docker shortcut commands

```
$ dhelp
``` 

