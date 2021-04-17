# Building Projects Branch

[![java](https://img.shields.io/badge/%20-java-red)](https://docs.oracle.com/en/java/javase/15/) 
[![ant](https://img.shields.io/badge/%20-ant-violet)](https://ant.apache.org/manual/index.html)

[ant/tutorialspoint](https://www.tutorialspoint.com/ant/index.htm)

[Data type](https://www.tutorialspoint.com/ant/ant_data_types.htm)

[Targets](https://ant.apache.org/manual/targets.html#extension-points)

[Tasklist](https://ant.apache.org/manual/tasklist.html)

[Core Conditions](https://ant.apache.org/manual/Tasks/conditions.html)

1. The project structure:

***структура проекту***
---
	* The database scripts -  **db**
	* The java source -       **src**
	* The third party jar -   **bin\lib**
	* The java class -        **bin\classes**
	* The test class -        **bin\tests**
---
	* скрипти бази даних в папці **db**.
	* файли коду в папці **src**.
	* третьопартійні бібліотеки [jar] зберігаютья в папці **lib**.
	* java класи в папці **bin**.
	* test класи в папці **test**.
2. Declare the structure of our project with the following tags

***Декларуємо структуру нашого проекту наступними тегами***
```
	<property name="src.dir" value="src"/>
	<property name="lib.dir" value="lib"/>
	<property name="build.dir" value="bin\classes"/>
	<property name="test.dir"  value="bin\tests"/>
```

3. The master-classpath holds the classpath information. In this case, it includes the classes in the build 
folder and the jar files in the lib folder.

***Master-classpath містить інформацію про classpath. У цьому випадку
він включає класи у build і jar-файли в папці lib***
```
<path id="master-classpath">
		<fileset dir="${lib.dir}>
			<include name="*.jar"/>
		</fileset>
		<pathelement path="${build.dir}"/>
	</path>
```
4. The clean target that deletes the .class files.

***Clean - це ціль, яка видаляє  .class файли.***
```
<target name="clean" description="Clean output directories" if="class-file.exists">
		<delete>
         <fileset dir="${build.dir}/classes">
            <include name="**/*.class"/>
         </fileset>
      </delete>
	</target>
```

5. First of all, we create the build directory, if it does not exist, then, 
we execute the javac command (specifying jdk1.9 as our target compilation). 
We supply the source folder and the classpath to the javac task and ask it to drop the class files in ${build.dir} folder.

***Перш за все, ми створюємо каталог побудови, якщо він не існує, тоді,
ми виконуємо команду javac (вказавши jdk1.9 як нашу цільову компіляцію).
Ми надаємо вихідну папку та шлях до класу до завдання javac і просимо його скинути файли класу в папку ${build.dir}***
```
	<target name="build" depends="clean" description="Compile source java files">
		<mkdir dir="${build.dir}/classes"/>
		<javac destdir="${build.dir}" source="1.9" target="1.9">
			<src path="${src.dir}"/>
			<classpath refid="master-classpath"/>
		</javac>
	</target>	
```

This target depends on clean ie first we want to run clean to delete all .class files, and then run the target build.

***Ця ціль залежна від clean тобто спочатку ми хочемо запустити clean для видалення всіх .class  файлів, а далі запустити команду.***

---
Download given repository and run from root directory

***Завантажуйте даний репозиторій та запускайте з кореневого каталогу***
```
C:\rootDir\>ant
Buildfile: D:\prog\Projects\dashboard\helloWorld\helloAnt\build.xml
info:
     [echo] Hello World - Welcome our project
BUILD SUCCESSFUL
Total time: 0 seconds
```
