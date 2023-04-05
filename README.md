# Fabric `The Basics`

Fabric provides a basic suite of operations for executing local or
remote shell commands (normally or via sudo) and uploading/downloading
files, as well as auxiliary functionality such as prompting the running
user for input, or aborting execution.


### Install Fabric

Setting up fabric requires a set of packages to work properly,
for this lesson I will be exploring fabric v1.14, following this
set of commands:

```
$ pip3 uninstall Fabric
$ sudo apt-get install libffi-dev
$ sudo apt-get install libssl-dev
$ sudo apt-get install build-essential
$ sudo apt-get install python3.4-dev
$ sudo apt-get install libpython3-dev
$ pip3 install pyparsing
$ pip3 install appdirs
$ pip3 install setuptools==40.1.0
$ pip3 install cryptography==2.8
$ pip3 install bcrypt==3.1.7
$ pip3 install PyNaCl==1.3.0
$ pip3 install Fabric3==1.14.post1
```

Alternatively, the script `install_fabric.sh` contains the commands
above -- save a few copy and paste.
