---
layout: post
title: uploading local project to GitHub
categories: [git test]
---


If you have been working on a project and now want to upload it to a new GitHub-repository, you have to do the following:

1. create a new repo at GitHub: GitHub provides you with the ssh-address
1. go into your project directory ```cd <project>```
2. If you want a readme-file ```touch README.md```
3. initialize your repository ```git init```
4. add your working files ```git add README.md``` and all you want in your repo
1. if you have empty directories and want them to show up in the repo, put a file in there: ```touch src/main/java/.gitkeep```
5. commit ```git commit -m "project xyz ..."```
6. add a remote ```git remote add origin git@github.com:<username>```
7. push it up ```git push -u origin master```

and you are ready!

D2I done right
================


Projektstruktur einrichten
----------------------------------------

unter u:\ws folgende Verzeichnisstruktur einrichten:

    -- d2i
       |
       |
       +--- trunk
             |
             |
	         + --- eclipse
	         |
	         |
	         + --- work


Setup
-------
* install STS 3.4.0 64bit
* configure STS.ini to your needs
* [make a shortcut]

STS Konfiguration
----------------------------
* start STS
* choose *"d2i/trunk/eclipse"* as workspace location
* goto "Install Extensions"
* choose 
    * Gradle Support
    * GroovyEclipse
    * Groovy 2.1 Compiler
* encoding für den workspace und alle neuen dateien auf utf-8 (=ISO10646) umstellen 


Projektstart
---------------------
1. Checkout project x
~~2. run `gradlew clean cleanEclipse` &#x21A9;~~
~~3. run `gradlew eclipse` &#x21A9; to build necessary *.classpath* and *.project* files~~
[4.0 start eclipse]
4. import gradle-project into eclipse (from within eclipse)
    * _Run before_ muss ausgewählt sein
    * _Run after_ muss ausgewählt sein
    * _Enable dependency management_ NICHT auswählen
    * _Enable DSL Support_ nicht auswählen

5. mit der Entwicklung beginnen ...



1. develop
1. start tomcatRun
1. debug


Projekt einrichten
====================
Gradleimport funktioniert nicht --> Problem mit Tomcat

* deswegen `gradlew eclipse`
* In STS ''Import existing project''
* --> groovy-all jar fehlt
* --> groovy-plugin fehlt
``` groovy
	apply plugin: 'groovy'

 	// groovy support
	compile "org.codehaus.groovy:groovy-all:${groovyVersion}:indy"
```
* compile "javax.validation:validation-api:1.0.0.GA"  einbauen







