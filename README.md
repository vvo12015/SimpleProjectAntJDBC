# Run java files and JDBC start Branch #
Run java files and scripts to delete and create sql tables
Запуск java файлів та скриптів для видалення та створення sql таблиць
 
[![java](https://img.shields.io/badge/%20-java-red)](https://docs.oracle.com/en/java/javase/15/) 
[![ant](https://img.shields.io/badge/%20-ant-violet)](https://ant.apache.org/manual/index.html)
[![ivy](https://img.shields.io/badge/%20-ivy-success)](http://ant.apache.org/ivy/index.html)
[![junit](https://img.shields.io/badge/%20-junit-red)](https://junit.org/junit5/)
[![jdbc](https://img.shields.io/badge/%20-jdbc-black)](https://docs.oracle.com/javase/tutorial/jdbc/basics/index.html)



[JDBC tutorials ant]()
[JDBC tutorialspoint](https://www.tutorialspoint.com/apache_ivy/apache_ivy_environment.htm)

1. Run target run java files created by you
Ціль, run запускає створені Вами java файли
<target name="run" description="run project" depends="build">
      <java fork="true" failonerror="yes" classname="org.hello.Main">
		 <classpath refid="master-classpath"/>
         <arg line="-u username -p 111"/>
      </java>
	</target>
2. Use the sql target to create a database and manipulate data(note that the database creation url is different from other urls)
Використовуючи ціль sql створюй DB та маніпулюй даними(зауваж, що для створення DB використовується інший url)
<sql driver="org.database.jdbcDriver"
     url="jdbc:database-url"
     userid="sa"
     password="pass"
     src="data.sql">
  <connectionProperty name="internal_logon" value="SYSDBA">
</sql>
For create DB use url of type - jdbc:postgresql://localhost:5432/?allowMultiQueries=true
For other url - jdbc:postgresql://localhost/yourDBname?create=true;
3. PosgreSQL:
- query for create the table
 запит на створення таблиці
	- CREATE TABLE QSESSION(
		QSESSION_ID BIGINT GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
		STATUS_REF BIGINT,
		USER_REF BIGINT,
		CURRENT_QUESTION_NUMBER SMALLINT,
		QUESTION_AMOUNT SMALLINT,
		TIME_REF BIGINT,
		CONSTRAINT QSESSION_STATUS
		  FOREIGN KEY(STATUS_REF) 
		  REFERENCES STATUS(STATUS_ID),
		CONSTRAINT USER_QSESSION
		  FOREIGN KEY(USER_REF) 
		  REFERENCES USERS(USER_ID)
);
- query for populate the table (запит на запонення таблиці)
	INSERT INTO USERS(NAME, PASSWORD, LOGIN, STATUS_REF)
	VALUES('Valentyn Vrakin', '111', 'vvo12015', 1);
- query for drop table (запис на видалення таблиці)
DROP TABLE IF EXISTS USER_ROLE CASCADE;