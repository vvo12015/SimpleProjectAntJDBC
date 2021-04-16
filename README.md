# HelloAntWithProperties Branch
 Studying the topic of working with properties
 Вивчення теми по роботі з properties 
 
[![java](https://img.shields.io/badge/%20-java-red)](https://docs.oracle.com/en/java/javase/15/) 
[![ant](https://img.shields.io/badge/%20-ant-violet)](https://ant.apache.org/manual/index.html)

[ant/tutorialspoint](https://www.tutorialspoint.com/ant/index.htm)

1. Properties can be set directly in build.xml file
	This in current project set property "customProperty" with value "--valueTest--"
2. Properties can be set in separate file, for example "build.properties" and configure it in build.xml throught tag 
	```<property file="build.properties"/>``` thus be given variables as host, user and password
3. Ant also has default [variables](https://www.tutorialspoint.com/ant/ant_property_task.htm). To illustrate working with the default properties, the ant.version property was used in the project
---

1. Властивості можуть бути задані безпосередньо в build.xml файлі
	В цьому конкретному проекті цій кейс показує властивість "customProperty" із значенням "--valueTest--"
2. Властивості можуть бути задані в окремому файлі, для прикладу "build.properties" для того, щоб Ant знайшов цей файл його потрібно зазначити в build.xml з допомогою теги 
	```<property file="build.properties"/>``` таким чином були зображені наступні змінні host, user and password
3. Ant також має значення по умовчанню [variables](https://www.tutorialspoint.com/ant/ant_property_task.htm). Для ілюстрації роботи з ними було використано ant.version.


Download given repository and run from root directory

Завантажте даний репозиторій та запустіть з кореневого каталогу
```
C:\rootDir\>ant
Buildfile: D:\prog\Projects\dashboard\helloWorld\helloAnt\build.xml

info:
     [echo]  Hello World - Welcome our project
     [echo]  Demonstration use default property
     [echo]  For example - prop ant.version: Apache Ant(TM) version 1.9.15 compiled on May 10 2020
     [echo]  This is our custom property --valueTest--
     [echo]  This is example to use of properties load from external file
     [echo]  Properties for to connect to DB
     [echo]  host - localhost
     [echo]  user - posgres
     [echo]  password - 111
     [echo]  changed property ant.project.name that equals - Hello Ant and JDBC WITH PosrgeSQL

BUILD SUCCESSFUL
Total time: 0 seconds
```
