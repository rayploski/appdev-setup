+++
title="Java"
type="page"
weight=80
+++



# Java
Our customers and prospects run on various versions of Java (some even 4-5 years old)!  Here's the latest recommended way to install various JDKs from Oracle, OpenJDK and even Azul.  We will install and manage multiple versions of Java on MacOS.


## Installation

### Manage multiple JVMs with jenv



First you should check if Java is already installed

    $ java -version

If you see an output like below then Java is already installed on your machine so skip to _Add Java to PATH_.

    java version "1.8.0_45"
    Java(TM) SE Runtime Environment (build 1.8.0_45-b14)
    Java HotSpot(TM) 64-Bit Server VM (build 25.45-b02, mixed mode)

If you don't see the output like above then you need to install Java on your system.

### Using the Oracle installer

Please download the macOS version from the [Oracle website](http://www.oracle.com/technetwork/java/javase/downloads/index.html).

### Using Homebrew

    brew update
    brew tap caskroom/versions

Then, install latest version of Java 10 via:

    brew cask install java


or install Java 8 using:

    brew cask install java8

Check if Java is correctly installed by running the `java -version` command again.

## Add Java to PATH

Add `JAVA_HOME` to your environment variables by adding the line below to your `env.sh` (see [iTerm2](/mac-setup/iTerm/README.html) section if you don't have a `env.sh` file).

    export JAVA_HOME="`/usr/libexec/java_home -v 1.8`"

If you are using Java 10, use the following:

    export JAVA_HOME="`/usr/libexec/java_home -v 10`"

You should have Java working now. Two popular IDE alternatives for writing Java are [Eclipse](https://www.eclipse.org/downloads/) or [IntelliJ](https://www.jetbrains.com/idea/download/).



## Install jenv
While it isn't a wholesale fix for the various java environments you may need, it does the trick for most use cases.  jenv will allow you to quickly switch from version to version of a JVM.  There are some tricks to getting it to work with various vendors (OpenJDK, Oracle, Azul)

    brew install jenv

## Install OpenJDK
Currently there is no "official" OpenJDK install via HomeBrew.  The best contibution out at the moment is AdoptOpenJDK.  

    brew tap AdoptOpenJDK/openjdk
    brew install <version>



## Install javadoc

    brew cask install java-jdk-javadoc
    ln -s  /usr/local/Caskroom/java-jdk-javadoc/10.0.1,10:fb4372174a714e6b8c52526dc134031e/docs/index.html ~/Desktop/javadoc.html


    # AdoptOpenJDK - HomeBrew TAP

## To use:

```bash
brew tap AdoptOpenJDK/openjdk
brew install <version>
```

## Versions

- adoptopenjdk-openjdk8
- adoptopenjdk-openjdk9
- adoptopenjdk-openjdk10