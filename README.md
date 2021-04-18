# JUnit Ant Branch #
Підключаннея JUnit
JUnit connection
 
[![java](https://img.shields.io/badge/%20-java-red)](https://docs.oracle.com/en/java/javase/15/) 
[![ant](https://img.shields.io/badge/%20-ant-violet)](https://ant.apache.org/manual/index.html)
[![ivy](https://img.shields.io/badge/%20-ivy-success)](http://ant.apache.org/ivy/index.html)
[![junit](https://img.shields.io/badge/%20-junit-red)](http://ant.apache.org/ivy/index.html)


[Ivy quick start](http://ant.apache.org/ivy/history/latest-milestone/tutorial/start.html)
[Ivy tutorialspoint](https://www.tutorialspoint.com/apache_ivy/apache_ivy_environment.htm)

0. Create test in java and save in ${srcTest.dir}
Створи тест на java і збережи в ${srcTest.dir}
```
package hello;

import static org.junit.Assert.*;

import org.junit.Test;

public class HelloTest{
	
	@Test
	public void testHello(){
		assertTrue(true);
	}
}
```

1. Define an XML namespace in your Ant file
Визначте простір імен XML у своєму файлі Ant
```
<?xml version="1.0"?>
<project name="Hello Ant and JDBC WITH PosrgeSQL" default="build"
	 xmlns:cpptasks="antlib:net.sf.antcontrib.cpptasks"
     xmlns:ivy="antlib:org.apache.ivy.ant"
     xmlns:junit4="antlib:com.carrotsearch.junit4"
     xmlns:mvn="antlib:org.apache.maven.artifact.ant">
....
```
2. Add new property of dir names
Додай нові властивості імен директорій
```
		<property name="src.dir" value="src/java"/>
		<property name="testSrc.dir" value="src/test"/>
		<property name="build.dir" value="bin"/>
		<property name="classes.dir" value="bin/classes"/>
		<property name="test.dir" value="bin/test"/>
		<property name="temp.dir" value="temp"/>
		<property name="lib.dir" value="lib"/>
		<property name="name" value="helloAnt"/>
		<property file="build.properties"/>
```
3. Add new dependencies ivy.xml
Додай нові залежності в ivy.xml
```
		<!-- https://mvnrepository.com/artifact/junit/junit -->
		<dependency org="junit" name="junit" rev="4.13.2"/>
		<!-- https://mvnrepository.com/artifact/org.hamcrest/hamcrest-core -->
		<dependency org="org.hamcrest" name="hamcrest-core" rev="2.2"/>
		<!-- https://mvnrepository.com/artifact/junit/junit -->
		<dependency org="com.carrotsearch.randomizedtesting" name="junit4-ant" rev="2.0.9"/>
```
4. Add new install-junit4 target that dependens on the resolve target
Додай нову ціль install-junit4, яка залежить від цілі resolve
```
<target name="install-junit4" depends="resolve" unless="junit4.available">
		<taskdef uri="antlib:com.carrotsearch.junit4">
		  <classpath>
			<fileset dir="${lib.dir}" includes="*.jar" />
		  </classpath>
		</taskdef>
		<property name="junit4.available" value="true" />
  </target>
```
5. Add to dependens list on compileUnitTest target install-junit4 target
Додай до списку залежностей compileUnitTest ціль install-junit4
```
<target name="compileUnitTest" depends="install-junit4, build" description="Compile test java files">
```
6. Add test target that run the tests. Given target depends on compileUnitTest
Додай test ціль, який запустить тести
```
<target name="test" description="run tests" depends="compileUnitTest">
    <junit4:junit4
      dir="${temp.dir}"
      maxmemory="100m"
      parallelism="auto">
     
       <classpath>
        <path location="${classes.dir}" />
        <path location="${test.dir}" />
        <fileset dir="${lib.dir}" includes="*.jar" />
      </classpath>
      <fileset dir="${test.dir}">
        <include name="**/*Test.class" />
      </fileset>
      <listeners>
        <junit4:report-text
        showThrowable="true"
        showStackTraces="true"
        showOutput="never"

        showStatusOk="true"
        showStatusError="true"
        showStatusFailure="true"
        showStatusIgnored="true"

        showSuiteSummary="false" />
        <!-- For enkins -->
        <junit4:report-ant-xml dir="${test.dir}/report" />
      </listeners>
    </junit4:junit4>
  </target>
```
7. Run from cmd
Запусти з командного рядка
```
ant test
Buildfile: D:\prog\Projects\dashboard\helloWorld\helloAnt\build.xml

clean:
   [delete] Deleting directory D:\prog\Projects\dashboard\helloWorld\helloAnt\bin

resolve:
[ivy:retrieve] :: Apache Ivy 2.5.0 - 20191020104435 :: https://ant.apache.org/ivy/ ::
[ivy:retrieve] :: loading settings :: url = jar:file:/D:/Program%20Files/apache-ant-1.9.15/lib/ivy-2.5.0.jar!/org/apache/ivy/core/settings/ivysettings.xml
[ivy:retrieve] :: resolving dependencies :: net.vrakin#AntJDBC_PostgreSQL;working@VVO12015
[ivy:retrieve]  confs: [default]
[ivy:retrieve]  found postgresql#postgresql;9.1-901-1.jdbc4 in public
[ivy:retrieve]  found junit#junit;4.13.2 in public
[ivy:retrieve]  found org.hamcrest#hamcrest-library;1.3 in public
[ivy:retrieve]  found org.hamcrest#hamcrest-core;2.2 in public
[ivy:retrieve]  found org.hamcrest#hamcrest;2.2 in public
[ivy:retrieve]  found com.carrotsearch.randomizedtesting#junit4-ant;2.0.9 in public
[ivy:retrieve]  found org.apache.ant#ant;1.8.2 in public
[ivy:retrieve]  found org.apache.ant#ant-launcher;1.8.2 in public
[ivy:retrieve]  found org.apache.ant#ant-junit;1.8.2 in public
[ivy:retrieve]  found com.google.guava#guava;10.0.1 in public
[ivy:retrieve]  found com.google.guava#guava-bootstrap;10.0.1 in public
[ivy:retrieve]  found asm#asm;3.3.1 in public
[ivy:retrieve]  found commons-io#commons-io;2.3 in public
[ivy:retrieve]  found com.google.code.gson#gson;2.0 in public
[ivy:retrieve]  found org.simpleframework#simple-xml;2.6.2 in public
[ivy:retrieve]  found stax#stax-api;1.0.1 in public
[ivy:retrieve]  found stax#stax;1.2.0 in public
[ivy:retrieve]  found xpp3#xpp3;1.1.3.3 in public
[ivy:retrieve]  found com.carrotsearch.randomizedtesting#randomizedtesting-runner;2.0.9 in public
[ivy:retrieve] :: resolution report :: resolve 612ms :: artifacts dl 55ms
[ivy:retrieve]  :: evicted modules:
[ivy:retrieve]  org.hamcrest#hamcrest-core;1.3 by [org.hamcrest#hamcrest-core;2.2] in [default]
[ivy:retrieve]  junit#junit;4.10 by [junit#junit;4.13.2] in [default]
        ---------------------------------------------------------------------
        |                  |            modules            ||   artifacts   |
        |       conf       | number| search|dwnlded|evicted|| number|dwnlded|
        ---------------------------------------------------------------------
        |      default     |   21  |   0   |   0   |   2   ||   27  |   0   |
        ---------------------------------------------------------------------
[ivy:retrieve] :: retrieving :: net.vrakin#AntJDBC_PostgreSQL
[ivy:retrieve]  confs: [default]
[ivy:retrieve]  27 artifacts copied, 0 already retrieved (9984kB/84ms)

install-junit4:

build:
    [mkdir] Created dir: D:\prog\Projects\dashboard\helloWorld\helloAnt\bin\classes
    [javac] Compiling 1 source file to D:\prog\Projects\dashboard\helloWorld\helloAnt\bin\classes
    [javac] warning: [options] system modules path not set in conjunction with -source 9
    [javac] 1 warning

compileUnitTest:
    [mkdir] Created dir: D:\prog\Projects\dashboard\helloWorld\helloAnt\bin\test
    [javac] Compiling 1 source file to D:\prog\Projects\dashboard\helloWorld\helloAnt\bin\test
    [javac] warning: [options] system modules path not set in conjunction with -source 9
    [javac] 1 warning

test:
[junit4:junit4] <JUnit4> says salut! Master seed: FEB4C52E2B182931
[junit4:junit4] Your default console's encoding may not display certain unicode glyphs: windows-1251
[junit4:junit4] Executing 1 suite with 1 JVM.
[junit4:junit4]
[junit4:junit4] Started J0 PID(4980@VVO12015).
[junit4:junit4] OK      0.00s | HelloTest.testHello
[junit4:junit4] JVM J0:     0.40 ..     1.03 =     0.63s
[junit4:junit4] Execution time total: 1.04 sec.
[junit4:junit4] Tests summary: 1 suite, 1 test

BUILD SUCCESSFUL
Total time: 3 seconds
```