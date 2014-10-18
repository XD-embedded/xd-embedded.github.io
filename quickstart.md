---
title: XD-embedded Quickstart
author: Esben Haabendal
---

# XD-embedded Quickstart

XD-embedded consists of two components: XD-tool and the XD-build core.

To start working on XD-embedded, you need to

1. Install XD-tool
2. Create XD-embedded manifest with XD-build core layer

## Install XD-tool

To install XD-tool, you currently have two options:

1. Run from source (git repo)
2. Install from PyPi

### Run from source

This is currently the recommended way to use XD-tool.  By using this, you will
be able to help out with XD-tool development, either by digging into the code
yourself, or by reporting issues, and easily test out proposed solutions.

To run from source, checkout the XD-tool repository:

```sh
git clone https://github.com/XD-embedded/xd-tool.git
```

Next, you should either put the bin/ subdir of the xd-tool repository in your
$PATH, or make a symlink to bin/xd from somewhere in your $PATH.

In order to use XD-tool, you also need to have the Python sh library.  On
Debian, you get it by running:

```sh
sudo apt-get install python3-sh
```

### PyPi install

If you want to use a release version of XD-tool, you can install from PyPi.
The package name is 'XD-tool'.  This is also a good approach if you don't want
to make any changes to XD-tool.

To install with pip on Debian, run:

```sh
pip3 install XD-tool
```

Keep in mind that you need to use the Python 3 pip command, which is 'pip3' on
Debian.  Other distros might have Python 3 pip as 'pip'.

If you are missing pip3 (again, assuming you are using Debian), run

```sh
sudo apt-get install python3-pip
```

In order to use XD-tool, you also need the git command.  On Debian, you get it
by running:

```sh
sudo apt-get install git
```

## Create manifest

To create an XD-embedded manifest with an XD-build core layer, do this:

```sh
mkdir xd-build
cd xd-build
xd init
xd layer add build/core
```

For the 'xd init' command to succeed, you need to have git configured (which you probably already have, if you are using git for something else).

```sh
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```
