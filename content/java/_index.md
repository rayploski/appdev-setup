+++
title="Java"
type="page"
weight=80
+++



# Java
Our customers and prospects run on various versions of Java (some even 4-5 years old)!  Here's the latest recommended way to install various JDKs from Oracle, OpenJDK and even Azul.  We will install and manage multiple versions of Java on MacOS.


### Using Homebrew

    brew update
    brew tap caskroom/versions

Then, install latest version of Java 10 via:

    brew cask install java


or install Java 8 using:

    brew cask install java8

Check if Java is correctly installed by running the `java -version` command again.

## Install OpenJDK
Currently there is no "official" OpenJDK install via HomeBrew.  The best contibution out at the moment is AdoptOpenJDK.  

    brew tap AdoptOpenJDK/openjdk
    brew install <version>


#### Versions

- adoptopenjdk-openjdk8
- adoptopenjdk-openjdk9
- adoptopenjdk-openjdk10


### Using the Oracle installer

Optional:  While not our preferred JDK, you can  download the macOS version from the [Oracle website](http://www.oracle.com/technetwork/java/javase/downloads/index.html).


### Manage multiple JVMs with jEnv
While it isn't a wholesale fix for the various java environments you may need, it does the trick for most use cases.  jenv will allow you to quickly switch from version to version of a JVM.  There are some tricks to getting it to work with various vendors (OpenJDK, Oracle, Azul)

    brew install jenv

#### Bash

    echo 'export PATH="$HOME/.jenv/bin:$PATH"' >> ~/.bash_profile
    echo 'eval "$(jenv init -)"' >> ~/.bash_profile

#### Zsh

    echo 'export PATH="$HOME/.jenv/bin:$PATH"' >> ~/.zshrc
    echo 'eval "$(jenv init -)"' >> ~/.zshrc

After installing jENV and updating your resource file, you can add and choose which jvm.

Find which JDK casks that are installed:

    $ ls /Library/Java/JavaVirtualMachines
    $ jdk-10.0.1.jdk   jdk-9.0.1.jdk    jdk1.8.0_121.jdk jdk1.8.0_131.jdk zulu-10.1,11.jdk 

Add each listing from your JavaVirtualMachines directory to jEnv _e.g._:

    jenv add /Library/Java/JavaVirtualMachines/jdk-10.0.1.jdk/Contents/Home
    jenv add /Library/Java/JavaVirtualMachines/jdk-9.0.1.jdk/Contents/Home

Add each listing from your OpenJDK JVMs to jEnv _e.g._:

    jenv add /usr/local/Cellar/adoptopenjdk-openjdk10/jdk-10+23/

More details on [jEnv](http://github.com/gcuisinier/jenv)


## Install javadoc
Brew allows for the installation of javadoc.  You will find it in your /usr/local/Caskroom/java-jdk-javadoc folder.

    brew cask install java-jdk-javadoc
    ln -s  /usr/local/Caskroom/java-jdk-javadoc/10.0.1,10:fb4372174a714e6b8c52526dc134031e/docs/index.html ~/Desktop/javadoc.html


