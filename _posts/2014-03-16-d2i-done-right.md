---
layout: post
title: d2i done right
categories: [d2i spring sts]
---


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

* spock und spock-eclipse fehlt

Gradle-Tomcat-Plugin
======================
* Tomcat-configuration: ```/src/main/webapp/META-INF/context.xml``` is used by tomcatRun


Spring and JPA
==================
* in ```@Service``` you can use ```@Autowired ApplicationContext ctx``` and then ```ctx.getBean(...)```

