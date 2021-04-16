# HelloAnt Branch
Create the initial build.xml file:
Створення початкового build.xml файлу
 
[![java](https://img.shields.io/badge/%20-java-red)](https://docs.oracle.com/en/java/javase/15/) 
[![ant](https://img.shields.io/badge/%20-ant-violet)](https://ant.apache.org/manual/index.html)

[ant/tutorialspoint](https://www.tutorialspoint.com/ant/index.htm)

1. Introduction to the basic elements of the build.xml file
Ознайомлення з основними  елементами build.xml  файлу
* project
	- name
	- default 
		specifies which target should be considered as the default
		визначає, яка ціль буде виконана в любому випадку
	- basedir(optional)(необов'язковий)
* target
	- name
	- depends
	- description
	- if
	- unless

Download given repository and run from root directory
```
C:\rootDir\>ant
Buildfile: D:\prog\Projects\dashboard\helloWorld\helloAnt\build.xml
info:
     [echo] Hello World - Welcome our project
BUILD SUCCESSFUL
Total time: 0 seconds
```
