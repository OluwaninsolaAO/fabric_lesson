# Fabric `The Basics`

Fabric provides a basic suite of operations for executing local or
remote shell commands (normally or via sudo) and uploading/downloading
files, as well as auxiliary functionality such as prompting the running
user for input, or aborting execution.

Using Fabric, you can write Python scripts that can execute shell
commands on one or more remote servers with just a few lines of code.
Fabric makes it easy to automate repetitive tasks and deploy
applications to multiple servers in parallel.

Fabric provides a number of useful features, including the ability
to define tasks, execute commands over SSH, upload and download files,
and interact with remote shells. It also has an extensive API for
managing SSH connections and handling output from remote commands.

Fabric is a powerful tool for managing remote servers and automating
deployment workflows. It is widely used in the DevOps community and is a
valuable tool for anyone who needs to manage remote servers on a
regular basis.


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
above -- save a few copy and paste. On success, fabric will be
available on your machine with the name `fab`.

```
$ fab task1 task2
```


### Create a Fabric script

Just like any other python script, Create a new file -- by convention
fabric scripts is usually named `fabfile.py` or just `fabfile`. This
might not always be the case, the use of `-f` flag can be used to
specify a path to a fabfile.


Fabric script example `fabfile.py`.
```
from fabric.api import run

def system_info():  # A task named system_info
	run('uname -a')
```

Execute `fabfile.py` using:
```
$ fab -f fabfile.py -H localhost,192.168.8.115 system_info
```
In the command above, `-f` specifies a fabfile to be used (optional,
defaults to `fabfile` or `fabfile.py` in the current working directory),
and `-H` defines a list of hosts delimeted by a comma (no space)
then followed by the `system_info` the name of the task to run.
