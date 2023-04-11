

## Introduction

AGE is a PostgreSQL extension that provides graph database functionality. It enables users to use graph querying as well as modelling on a relational database.

The purpose of this post is to help Mac users (such as myself) to install and use AGE.


## Installing PostgreSQL from Source Code.

For starters it is important to note that you will need to download and install either version 11 or 12. Any other versions are currently not compatible with AGE. If you have versions superseding 11/12 you'll have to downgrade or install.

**1. Install Dependencies**

A preliminary step and general good practice is to make sure you have all the dependencies required to run AGE installed beforehand.

Homebrew is a package manager for MacOS which is extremely popular. You can use this to install all the dependencies and PostgreSQL as well but later on in this post I'll showcase the steps to do so manually.

If you don't have Homebrew in your Mac you can use this command:

`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"`

Now make sure to install these dependencies with Homebrew using this command:

`brew install [package-name]`

The packages are:

- readline openssl
- zlib
- flex
- bison

Once you're done, simply move on to the next step.

**2. Download PostgreSQL from Source Code**

You can download the appropriate version (11 or 12) from the official PostgreSQL website [here](https://www.postgresql.org/ftp/source/).

Once you have the files, you can simply click on them to unzip. This will unzip the file into the directory you're currently present in, which in my case was Downloads.

You can also use this command to directly download and unzip version 11.

`curl -O https://ftp.postgresql.org/pub/source/v11.0/postgresql-11.0.tar.gz && tar -xvf postgresql-11.0.tar.gz && rm -f postgresql-11.0.tar.gz`

Navigate to the file folder with postgresql files. You can use the 'ls' command to make sure you're in the right directory. Then simply in your terminal use these commands:


```
./configure --enable-debug --enable-cassert --prefix=$(pwd) CFLAGS="-glldb -ggdb -Og -g3 -fno-omit-frame-pointer"
//This will invoke the .configure file present in the directory to create a Makefile we can use
make 
make install /to finally install

```

Ignore warnings (not fatal errors), and you should have a message at the end that displays "PostgreSQL installed successfully.

_An alternate approach is to invoke the terminal in bash shell and follow the same steps in that prompt. To do this simply open a terminal and type in `bash` to go into bash shell_

And you're done installing your preferred version of PostgreSQL by this step!

## Installing Apache AGE

To get Apache AGE, we must first get the files from Github which can be done simply by cloning the repository. For this, please make sure you already have Git installed to your Mac. If you don't, you can follow [this](https://github.com/git-guides/install-git) to get Git.

**3. Cloning AGE repository**

First make sure you're in a directory of your choosing, this can be the same as the folder you chose to install PostgreSQL.

Open the terminal, same as before and use this command:

`git clone https://github.com/apache/age.git`

So now that you have AGE in your Mac, it is time to install it.
Simply run these commands:

```
cd age //Make sure you're in the directory that contains the files of Age
sudo make PG_CONFIG=[pathname]/pg_config install;
```
For [pathname], you can first look for the pg_config file that will be present in the bin folder for postgresql. Copy that as a file-path and use it. 

Once done you can run some tests to make sure everything is running smoothly! One such test is the installcheck command.

## References

- https://stackoverflow.com/questions/75454749/error-installing-age-from-source-code-on-mac
- https://age.apache.org/age-manual/master/intro/setup.html
- https://www.postgresql.org/docs/current/install-procedure.html

---

Contribute to Apache AGE
Apache AGE website: https://age.apache.org/

Apache AGE Github: https://github.com/apache/age
