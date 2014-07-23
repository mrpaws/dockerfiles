dockerfiles
===========

collection of dockerfiles

ubuntu:
Personal base image of Ubuntu 14.04 with SSH and env configured.

percona*:
MySQL 5.5 container:
  - Expects a volume called '/dbdata' for tables.  If no tables found, mysql_install_db will be needed;
  - Available as a network service or just linked without port exposure.
  
  
