---
layout: post
title: HLA Certi, getting started !
date: '2016-04-10 20:43:25'
tags:
- dev-tutorials
---

HLA stands for High Level Architecture, a set of specifications for distributed simulation systems that originated from the US Department of Defense (DoD) around 1996. (Needs citation)

#### HLA Overview

###### Concepts
ToDO

###### Features

#### Certi

Certi is an open-source implementation of HLA specifications. It provides a HLA Runtime Infrastruture (RTI), a Federation Ambassador module and APIs to build a HLA federation.

#### Compiling CERTI

###### Predependencies
You will need to install `Cmake` and have `GCC` installed on your Linux system. I found it mandatory to install `YACC` and `LEX` as well. `libxml2-dev` is optional, you want to install it to be able to export/import federations.
```
sudo apt-get install build-essential cmake sudo byacc flex libxml2-dev
```
###### Build Certi from sources
The first thing to do to work with Certi is to get the sources from Certi's git forge.
Then create a build folder.

```bash
git clone git://git.savannah.nongnu.org/certi.git
cd certi
mkdir build
cd build
```

Run Cmake by picking an installation folder `installFolder` and compile with make. In `make -jn`, replace `n` with the number of cores to speed up compilation.

```bash
cmake -DCMAKE_ISNTALL_PREFIX=/installFolder ..
make -j4
make install
```

When using recent versions of GCC, compilation might fail with the following error message:
```bash
[ 66%] Linking CXX executable TestFedTime
libFedTimed.so.1.0.0: undefined reference to `typeinfo for RTI::Exception`
```

This is due to a cyclical dependency (FedTime is supposed to throw RTI::Exception) not declared in CMake (to make it work). However, throwing exceptions requires a [typeinfo lookup](https://gcc.gnu.org/wiki/Visibility) which triggers GCC's error. Making RTI::Exception destructor purely virtual seems to fix the problem. (Probably because in the absence of non-inline virtual methods, GCC copies the typeinfo to all relevant translation units, [see here](https://gcc.gnu.org/onlinedocs/gcc/Vague-Linkage.html).

Last step is to run a script to setup the approriate environment variables.

```bash
source installFolder/myCERTI_env.sh
```

I recommand to add this line at the end of your `~/.bashrc` file so that you don't have to rerun it everytime.

#### Getting started with HLA Certi

Now we want to run the CERTI tutorial.
First, clone the applications repository

```bash
git clone git://git.savannah.nongnu.org/certi/applications.git Certi-Apps
```

It's now time to build the tutorial:
```
cd Certi-Apps/HLA_Tutorial
mkdir build
cd build
cmake -DCMAKE_ISNTALL_PREFIX=appsInstallFolder ..
make
make install
```

Now open three terminals and run respectively:
1. `cd` into `appsInstallFolder/share/federations`. Launch the Runtime `rtig`
2. Launch the tutorial controller app `appsInstallFolder/bin/controllerFederate`
3. Launch the tutorial process app `appsInstallFolder/bin/processFederate`

Then terminal `2` should guide you through the the tutorial, make sure you observe the three terminals outputs during the execution of the tutorial.

Sources:

* https://gcc.gnu.org/wiki/Visibility
* https://gcc.gnu.org/onlinedocs/gcc/Vague-Linkage.html
* http://www.nongnu.org/certi/certi_doc/Install/html/build.html
