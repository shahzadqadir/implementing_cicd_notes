h1 Steps to install Gradle

Gradle Needs minimum Java 8

```
Centos Distribution
sudo yum install -y java-1.8.0-openjdk unzip

Ubuntu distribution
sudo apt install -y java-1.8.0-openjdk && apt install -y unzip

```

Download and Install Grale

```
wget -O gradle-8.9.zip https://services.gradle.org/distributions/gradle-8.9-bin.zip?_gl=1*112ad7c*_gcl_au*ODQzODAyMDMuMTcyMzUzMTgzNQ..*_ga*MTA5MDcwMjY4OS4xNzIzNTMxODM1*_ga_7W7NC6YNPT*MTcyMzUzMTgzNS4xLjEuMTcyMzUzMjQ5OC42MC4wLjA. 
```

Link above is copied from Gradle website. -O flag specifies output file

Create a Directory and unzip Gradle into it

```

mkdir /opt/gradle
sudo unzip -d /opt/gradle gradle-8.9.zip
```

Add Gradle to environment path

```
sudo vi /etc/profile.d/gradle.sh

export PATH=$PATH:/opt/gradle-8.9/bin
```

set Permissions to above script

```
sudo chmod 755 /etc/profile.d/gradle.sh
```

Test installation

```
Logout and Log back in then
gradle --version

[cloud_user@8cc813181c1c ~]$ gradle --version

Welcome to Gradle 8.9!

Here are the highlights of this release:
 - Enhanced Error and Warning Messages
 - IDE Integration Improvements
 - Daemon JVM Information

For more details see https://docs.gradle.org/8.9/release-notes.html


------------------------------------------------------------
Gradle 8.9
------------------------------------------------------------

Build time:    2024-07-11 14:37:41 UTC
Revision:      d536ef36a19186ccc596d8817123e5445f30fef8

Kotlin:        1.9.23
Groovy:        3.0.21
Ant:           Apache Ant(TM) version 1.10.13 compiled on January 4 2023
Launcher JVM:  1.8.0_412 (Red Hat, Inc. 25.412-b08)
Daemon JVM:    /usr/lib/jvm/java-1.8.0-openjdk-1.8.0.412.b08-1.el7_9.x86_64/jre (no JDK specified, using current Java home)
OS:            Linux 3.10.0-1160.119.1.el7.x86_64 amd64
```

Gradle wrapper can download/install required version of Gradle on the client machine, only requirement is Java 8 or later.

You can install Gradle Wrapper easily using ``gradle wrapper``command. You will need to add .gradle to your .gitignore file.

Making Project with Gradle Wrapper

```
mkdir my-project && cd my-project
gradle init
gradle wrapper

```

Next time to build gradle project all you need is ``./gradlew build`` command
