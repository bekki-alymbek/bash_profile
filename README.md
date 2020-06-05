
# What is Bash profile and differences between bashrc.
- .bash_profile is executed for login shells, while .bashrc is executed for interactive non-login shells.

- When you login (type username and password) via console, either sitting at the machine, or remotely via ssh: .bash_profile is executed to configure your shell before the initial command prompt.

- But, if you’ve already logged into your machine and open a new terminal window (xterm) then .bashrc is executed before the window command prompt. .bashrc is also run when you start a new bash instance by typing /bin/bash in a terminal.

# Commands for Environment Variables

`env`  – The command lists all of the environment variables in the shell.

`printenv` – The command prints all (if no environment variable is specified) of environment variables and definitions of the current environment.

`set` – The command assigns or defines an environment variable.

`unset` – The command deletes the environment variable.

`export` – The command exports the value of the newly assigned environment variable.

# Creating functions

```
function setproxy() {
        export http_proxy='http://proxy.com:8080'
        export https_proxy='http://proxy.com"8080'
        export no_proxy='localhost,127.0.0.1,*.allstate.com'
}
```
```
function noproxy() {
        unset http_proxy
        unset https_proxy
}
```

## get the alias and functions
```
if [ -f ~/etc/bashrc ]: then
        . ~/etc/bashrc
fi
```
- How to force your current session to read the file by just updating it.
```
source ~/.bash_profile  
```
or

```
. ~/.bash_profile
```
and

```
source ~/etc/bashrc

```

- depends on where your .bashrc file is located.

# Creating alias

 Alias can be create in either .bash_profile or .bashrc files. But once you add the alias into your .bash_profile, you must source it before your alias will be available to execute  

# Environmental Variables

Environmental variables are variables that are defined for the current shell and are inherited by any child shells or processes. Environmental variables are used to pass information into processes that are spawned from the shell.

- Additional information about environmental variables: [How to read and set environmental and shell variables on a linux](https://www.digitalocean.com/community/tutorials/how-to-read-and-set-environmental-and-shell-variables-on-a-linux-vps)
