# HelloAnt Branch
Create the initial build.xml file:

Створення початкового build.xml файлу
 
[![java](https://img.shields.io/badge/%20-java-red)](https://docs.oracle.com/en/java/javase/15/) 
[![ant](https://img.shields.io/badge/%20-ant-violet)](https://ant.apache.org/manual/index.html)

[ant/tutorialspoint](https://www.tutorialspoint.com/ant/index.htm)

Introduction to the basic elements of the build.xml file

Ознайомлення з основними  елементами build.xml  файлу
* project
	- **name**(Required)(обов'язковий)
	- **default** (optional)
		specifies which target should be considered as the default
		визначає, яка ціль буде виконана в любому випадку
	- **basedir**(optional)(необов'язковий)
* target
	- **name**(required)(обов'язковий)
	- **depends**(optional) - Comma separated list of all targets that this target depends on. (Optional) (***Список цілей розділений комами, пов'язаних з даною цілю цілей. Тобто без виконання, яких дана ціль не запускається***)
	- **description**(optional) - (***опис***)
	- **if**(optional) - condition for fulfilling this goal (***умова виконання даної цілі***)
	- **unless**(optional) 	- Adds the target to the dependency list of the specified Extension Point. An Extension Point is similar to a target, but it does not have any tasks. (Optional) (***Додає ціль до списку залежностей вказаної точки розширення. Точка розширення схожа на ціль, але вона не має жодних завдань. (Необов’язково)***)
	- **extensionOf**	Adds the current target to the depends list of the named extension-point. since Ant 1.8.0.(***додавання поточної цілі до списку залежностей в extension-point***)
	- **onMissingExtensionPoint**	What to do if this target tries to extend a missing extension-point. (fail, warn, ignore). since Ant 1.8.2.(***що робити якщо ціль намагається розширити extension-point якого не існує (fail, warn, ignore)***)
				

Download given repository and run from root directory
Завантажте даний репозиторій та виконайте дії з кореневого каталогу
```
C:\rootDir\>ant
Buildfile: D:\prog\Projects\dashboard\helloWorld\helloAnt\build.xml
info:
     [echo] Hello World - Welcome our project
BUILD SUCCESSFUL
Total time: 0 seconds
```
