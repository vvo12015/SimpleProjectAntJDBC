# SimpleProjectAntJDBC
 
 [ant.apache.org](https://ant.apache.org/manual/index.html)
 [www.postgresql.org](https://www.postgresql.org/docs/current/tutorial-start.html)
 [Java JDBC API](https://docs.oracle.com/javase/tutorial/jdbc/basics/index.html)
 
 
 [ant/tutorialspoint](https://www.tutorialspoint.com/ant/index.htm)
 [posgresql/tutorialspoint](https://www.tutorialspoint.com/postgresql/index.htm)
 [jdbc/tutorialspoint](https://www.tutorialspoint.com/jdbc/index.htm)

Це маленький простий проект, який допоможе розібратися в основних можливостях Ant на прикладі роботи з JDBC API
з базою даних PosgreSQL.
Структура ant-проекту взята з [docs.oracle.com](https://docs.oracle.com/javase/tutorial/jdbc/basics/index.html) 
як і принципи написання.

##Technologies to be used

Технології, які будуть використані

*Ant
*JDBC
*PosgreSQL
*Hosting provider 
[ElephantSQL](https://www.elephantsql.com/)

## Prerequisites
-Install Ant 
	-[Installing Ant](https://ant.apache.org/manual/install.html#installing)
	-[Ant - Environment Setup](https://www.tutorialspoint.com/ant/ant_environment.htm)
		-Download Ant binary directory
		-Set the ANT_HOME environment variable to the directory where you installed Ant. 
		-Set the JAVA_HOME environment variable (see the Advanced section below). 

-Install PosgreSQL
	-Download [Windows installers](https://www.postgresql.org/download/windows/)
	-Run installer PosgresSQL
-Log in or sing up hosting for PostgreSQL or use local DB
	-Log in [elephantsql.com](https://customer.elephantsql.com/)
	-Create New Instance

1. Ознайомлення з основними можливостями ant
	-create build.xml for HelloWorld
	-project xml element:
		-name
		-default 
			specifies which target should be considered as the default
		
			визначає, яка ціль буде виконана в любому випадку
		-basedir(optional)(необов'язковий)
