# SimpleProjectAntJDBC
 
[![java](https://img.shields.io/badge/%20-java-red)](https://docs.oracle.com/en/java/javase/15/) 
[![ant](https://img.shields.io/badge/%20-ant-violet)](https://ant.apache.org/manual/index.html)
[![ivy](https://img.shields.io/badge/%20-ant-success)](http://ant.apache.org/ivy/index.html)
[![posgreSQL](https://img.shields.io/badge/%20-posgresql-blue)](https://www.postgresql.org/docs/current/tutorial-start.html)
[![jdbc](https://img.shields.io/badge/%20-jdbc-black)](https://docs.oracle.com/javase/tutorial/jdbc/basics/index.html)

[ant/tutorialspoint](https://www.tutorialspoint.com/ant/index.htm)

[posgresql/tutorialspoint](https://www.tutorialspoint.com/postgresql/index.htm)

[jdbc/tutorialspoint](https://www.tutorialspoint.com/jdbc/index.htm)

This is a small simple project that will help to understand the basic features of Ant on the example of working with the JDBC API with the PosgreSQL database. The structure of the ant-project is taken from docs.oracle.com as well as the principles of writing.

Це маленький простий проект, який допоможе розібратися в основних можливостях Ant на прикладі роботи з JDBC API
з базою даних PosgreSQL.
Структура ant-проекту взята з [docs.oracle.com](https://docs.oracle.com/javase/tutorial/jdbc/basics/index.html) 
як і принципи написання.
## Technologies to be used
Технології, які будуть використані
* Ant
* JDBC
* PosgreSQL
* Hosting provider 
[ElephantSQL](https://www.elephantsql.com/)
## Prerequisites
- Install Ant 0
	- [Installing Ant](https://ant.apache.org/manual/install.html#installing)
	- [Ant - Environment Setup](https://www.tutorialspoint.com/ant/ant_environment.htm)
		- Download Ant binary directory
		- Set the ANT_HOME environment variable to the directory where you installed Ant. 
		- Set the JAVA_HOME environment variable (see the Advanced section below). 
- Install PosgreSQL
	- Download [Windows installers](https://www.postgresql.org/download/windows/)
	- Run installer PosgresSQL
- Log in or sing up hosting for PostgreSQL or use local DB
	- Log in [elephantsql.com](https://customer.elephantsql.com/)
	- Create New Instance
## Basic steps
Оcновні кроки
- [create build.xml for HelloWorld](https://github.com/vvo12015/SimpleProjectAntJDBC/tree/helloAnt)
- [build with properties](https://github.com/vvo12015/SimpleProjectAntJDBC/blob/helloAntWithProperties/README.md)
- [build with init project](https://github.com/vvo12015/SimpleProjectAntJDBC/tree/buildingProjects)
