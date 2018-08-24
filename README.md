# Course Programming Environment

![Vagrant Up](./.imgs/vagrant_up.gif)

# VirtualBox and Vagrant

The best way to make sure your projects will work on the autograder is
to test it in the same environment. The autograder is an Ubuntu Linux
machine. Fortunately you can easily run Linux on a Mac or a Windows
machine using a “virtual machine”. Specifically we require that you
use [VirtualBox](https://www.virtualbox.org/), which runs on Mac,
Linux, and Windows and is free. We also request that you use
[Vagrant](https://www.vagrantup.com) to setup the VM and environment
tools.

The first discussion section will help you get your programming
environment setup for the projects and assignments. However, you are
expected to make sure your environment is ready and working before the
first project assignment.

# Setup

Setting up your virtual machine (VM) environment is easy:

1. Download [VirtualBox](https://www.virtualbox.org/).
1. Download [Vagrant](https://www.vagrantup.com).
1. Download
   [this](https://github.com/umass-cs-377/377_progenv/archive/master.zip)
   repository and unzip. You should now have a folder called
   `377_progenv-master`. You are welcome to change the name of this
   folder to anything you would like. We will refer to this as the
   PROGENV folder.
1. Open a command prompt on your operating system of choice. On a Mac
   this is the `Terminal` program. On Windows this is the `Command`
   program. On Linux - well, if you are using Linux already then you
   probably know about how to open up the shell. After you do this,
   then you need to enter into the PROGENV directory. You do this
   using the `cd` command.
1. Lastly, you need to build the VM. To do this, you run the following
   command:
   
   `$ vagrant up`
   
   Make sure you are connected to the internet. This command will
   download the VM image and install lots of packages to setup your
   very own programming environment for this course!
   
   Note: if you see the following:
   
   ```bash
   default: Warning: Connection reset. Retrying...
   default: Warning: Remote connection disconnect. Retrying...
   default: Warning: Connection reset. Retrying...
   default: Warning: Remote connection disconnect. Retrying...
   default: Warning: Connection reset. Retrying...
   default: Warning: Remote connection disconnect. Retrying...
   default: Warning: Connection reset. Retrying...
   ```
   
   Be patient - it will eventually connect.
   
After you have completed setting up the VM environment, you can login
to the virtual machine with this simple command:

```bash
$ vagrant ssh
```

If everything worked correctly you will login to the Linux VM and you
should see the prompt. At this point you can open up any of the
suggested editors and compile C/C++ programs.

It is also important to note that Vagrant will connect the PROGENV
folder on your host operating system's file system (e.g., Mac,
Windows, Linux) with the virtual machine operating system's file
system (Linux). That is, if you add a file into PROGENV on your host
OS you will see the file inside the VM. You can see this by navigating
to the `/vagrant` directory inside the VM:

```bash
$ cd /vagrant
```

If you run the `ls` command you will see the following:

```bash
$ ls -lR
total 16
-rw-r--r--  1 vagrant  vagrant  3613 Aug 24 16:59 README.md
-rw-r--r--  1 vagrant  vagrant   494 Aug 24 16:38 Vagrantfile
drwxr-xr-x  9 vagrant  vagrant   288 Aug 24 16:30 docs

./docs:
total 5336
-rw-r--r--@ 1 vagrant  vagrant   107375 Aug 24 16:29 bash-cheat.pdf
-rw-r--r--@ 1 vagrant  vagrant    53568 Aug 24 16:29 curl-cheat.pdf
-rw-r--r--@ 1 vagrant  vagrant   112637 Aug 24 16:29 emacs-cheat.pdf
-rw-r--r--@ 1 vagrant  vagrant   377767 Aug 24 16:29 git-cheat.pdf
-rw-r--r--@ 1 vagrant  vagrant  1785862 Aug 24 16:29 python-cheat.pdf
-rw-r--r--@ 1 vagrant  vagrant    44436 Aug 24 16:29 vagrant-cheat.pdf
-rw-r--r--@ 1 vagrant  vagrant   230787 Aug 24 16:29 vim-cheat.pdf
```

To test things out, run the following command from inside the
`/vagrant` directory:

```bash
$ echo "hello, world" > hello.txt
```

Now, from you host operating system navigate to the PROGENV folder and
look inside. You should see the `hello.txt` file. Voila, your VM
environment is now ready for this course!

# Cheatsheets

We have provided a number of "cheatsheets" in the `docs` folder that
you are welcome to use. They may be helpful when you begin learning
one of the editors below. 

# Programming Editors

We highly recommend that you learn one of the following editors for
this course:

* [emacs](https://www.gnu.org/software/emacs/)
* [vim](https://www.vim.org/)

Both of these editors can run inside your virtual machine terminal and
are exceptional tools of the trade. Although there is a steep learning
curve to learn these editors in a deep way, you can easily grasp the
basics of each editor to complete the work in this course. Learning
one of these editors will more than payoff in the future - trust
us!. Optionally, you may also use the simple and very unsophisticated
[nano](https://www.nano-editor.org/) editor if you are stuck. However,
we can't emphasize enough the importance of learning emacs or vim.

After you install the virtual machine for this course you can easily
run each of these editors from the terminal:

```bash
$ emacs
$ vim
$ nano
```

Although we **really** want you to learn either `vim` or `emacs`, you
are able to use an alternative editor from your host OS by
opening/saving files in the PROGENV directory. If you are a CS student
you should not discount the importance of learning one of these
editors - it will surely save your life in the future.
