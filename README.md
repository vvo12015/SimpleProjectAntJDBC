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
	- **name**
	- **depends** Coma separate list of target those depend this target (***список залежностей через кому після яких буде запущено дану ціль***)
	- **description**
	- **if** - the condition when run this target (***умова при які виконається дана ціль***)
	- **unless** - the name of the property that must not be set in order for this target to execute, or something evaluating to false (***ім'я властивості, яке не повинно бути встановлене для виконання цієї цілі, або щось, що оцінює як false***)
	- **extensionOf**	Adds the current target to the depends list of the named extension-point. since Ant 1.8.0.(***додавання поточної цілі до списку залежностей в extension-point***)
	- **onMissingExtensionPoint**	What to do if this target tries to extend a missing extension-point. (fail, warn, ignore). since Ant 1.8.2.(***що робити якщо ціль намагається розширити extension-point якого не існує (fail, warn, ignore)***)

Download given repository and run from root directory
```
C:\rootDir\>ant
Buildfile: D:\prog\Projects\dashboard\helloWorld\helloAnt\build.xml
info:
     [echo] Hello World - Welcome our project
BUILD SUCCESSFUL
Total time: 0 seconds
```
