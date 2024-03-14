# SQLMAP

SQLMap es una herramienta de código abierto diseñada para detectar y explotar vulnerabilidades de inyección de SQL en aplicaciones web. Permite a los investigadores de seguridad y a los profesionales de pruebas de penetración automatizar el proceso de identificación y explotación de fallos de seguridad en bases de datos relacionales a través de técnicas de inyección de SQL.
SQLMap automatiza el proceso de identificación y explotación de vulnerabilidades de inyección de SQL en aplicaciones web, permitiendo a los investigadores de seguridad y profesionales de pruebas de penetración llevar a cabo evaluaciones exhaustivas de seguridad en sistemas de bases de datos.

## Comandos básicos para SQLMAP
1. Identificar la URL vulnerable: Necesitas identificar la URL de la página que sospechas que es vulnerable a la inyección de SQL. Esta suele ser una URL que toma parámetros GET o POST y que utiliza estos parámetros para consultar una base de datos.
2. Recopilar información básica: Utiliza SQLMap para recopilar información básica sobre la vulnerabilidad. Puedes hacerlo ejecutando el siguiente comando:

~~~lua
sqlmap -u "URL" --dbs
~~~

Reemplaza "URL" con la URL que has identificado como vulnerable. Este comando intentará identificar las bases de datos disponibles en el servidor.

3. Enumerar tablas: Una vez que hayas identificado las bases de datos disponibles, puedes usar SQLMap para enumerar las tablas dentro de esas bases de datos. Puedes hacerlo con el siguiente comando:

~~~lua
sqlmap -u "URL" -D <database_name> --tables
~~~

Reemplaza <database_name> con el nombre de la base de datos que deseas explorar.

4. Extraer datos: Una vez que hayas identificado las tablas disponibles, puedes usar SQLMap para extraer datos de esas tablas. Puedes hacerlo con el siguiente comando:

~~~lua
sqlmap -u "URL" -D <database_name> -T <table_name> --dump
~~~

Reemplaza <table_name> con el nombre de la tabla de la que deseas extraer datos.

5. Enumeración de usuarios: SQLMap puede intentar enumerar los usuarios en la base de datos utilizando la opción --users. 

~~~lua
sqlmap -u "URL" --users
~~~

6. Ejecución de comandos SQL personalizados: Puedes ejecutar comandos SQL personalizados en el servidor utilizando la opción --sql-shell.

~~~lua
sqlmap -u "URL" --sql-shell
~~~

7. Ejecución de shell en el servidor: SQLMap también puede intentar ejecutar un shell interactivo en el servidor si se encuentra una vulnerabilidad grave. Puedes habilitar esto utilizando la opción --os-shell.

~~~lua
sqlmap -u "URL" --os-shell
~~~
