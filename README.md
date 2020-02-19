# Trigger_mysql_udf_windows
Tutorial untuk trigger mysql dengan sys_exec &amp; sys_val pada Windows

Login to mysql

check OS and version

> select @@version_compile_os, @@version_compile_machine;

check plugin direcatory, bisa d ganti di file my.ini;

> select @@plugin_dir;

download lib_mysqludf_sys

extensi .dll untuk windows dan .so untuk mac/linux

https://github.com/rapid7/metasploit-framework/tree/master/data/exploits/mysql atau clone repo ini

buat function untuk akses system

> CREATE FUNCTION sys_exec RETURNS int SONAME 'lib_mysqludf_sys_32.dll';

> CREATE FUNCTION sys_eval RETURNS string SONAME 'lib_mysqludf_sys_32.dll';

test function

menampilkan versi windows di layar

> SELECT sys_eval('ver');

akses php dengan curl -silent

> select sys_exec('curl --silent --output /dev/null http://www.keycdn.com/');
