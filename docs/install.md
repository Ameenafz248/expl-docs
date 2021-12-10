---
title: 'Installation'
---

# Installation

## Install LEX

=== "Ubuntu"

    ```bash
    sudo apt-get update
    sudo apt-get install flex
    ```

=== "Fedora"

    ```bash
    yum instal flex
    ```

## Install YACC


=== "Ubuntu"

    ```bash
    sudo apt-get update
    sudo apt-get install bison
    ```

=== "Fedora"

    ```bash
    yum install bison
    ```

## Install XSM Machine Simulator

The compiler's target code needs to be run on a simulator and the installation steps are given below.

Let us install XSM

### Step 1

Download XSM Simulator : [Version 1](files/xsm_expl.tar.gz)

### Step 2

Extract this file and navigate into the folder `xsm_expl` through the terminal.

Do the following steps:

1. Type `make`.
    
    You may get some warnings and they can be ignored. If you get any **fatal error**, then install the following dependencies and try running `make` again :
    ```bash
    sudo apt-get install libreadline-dev
    sudo apt-get install libc6-dev
    ```
    If any other dependencies are missing (this depends on your system configuration), you have to install the missing dependencies and run `make` again.

    !!! note "Optional"
        While running `./xsm` after Step 2 if you get this error:
        ```
        /usr/bin/ld: cannot find -ll collect2: error: ld returned 1 exit status
        ```
        Then you need to install:
        ```bash
        sudo apt-get install libfl-dev
        ```
        and edit the `Makefile` of `xsm_dev` folder, to proceed find the line where `-ll` is used as option
        and update it to ``-lfl`` to use the `flex` library we installed above.
        Now you can run `make` again after navigating into the folder `xsm_expl` through the terminal.
    
2. Type `cd ../xfs-interface/` and type `./init`.
3. (Optional) Add this line `#!/usr/bin/env bash` as first line to the `xsm` file in `xsm_expl` folder.
    This step is for those who don't have **bash** or **sh** as their "default shell" and therefore may be using other customizable shells like `zsh`, etc as their default shell.
    You can check your default shell by using `echo $SHELL` in terminal.

The usage instructions for the XSM simulator can be found [here](xsmusagespec.html).

Please report installation errors to _kmurali@nitc.ac.in_
