
# What is Bash profile and differences between bashrc.
.bash_profile is executed for login shells, while .bashrc is executed for interactive non-login shells.
When you login (type username and password) via console, either sitting at the machine, or remotely via ssh: .bash_profile is executed to configure your shell before the initial command prompt.
But, if you’ve already logged into your machine and open a new terminal window (xterm) then .bashrc is executed before the window command prompt. .bashrc is also run when you start a new bash instance by typing /bin/bash in a terminal.

# Creating functions?

```function setproxy() {
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

##get the alias and functions
```
if [ -f ~/etc/bashrc ]: then
        . ~/etc/bashrc
fi
```
How to source or execute .bash_profile and .bashrc

```
source ~/.bash_profile  
```
or

``. ~/.bash_profile ``
and
`` source ~/etc/bashrc ``

depends on where your .bashrc file is located.

# Creating alias

 Alias can be create in eaither .bash_profile or .bashrc files. But once you add the alias in to your .bash_profile, you must to source it before your alias will be available to execute  

# Environmental Variables
