from ubuntu:14.04
maintainer mrpaws "<paws@delimitize.com>"

env DEBIAN_FRONTEND noninteractive

run useradd -r -s /bin/false -c "MySQL Daemon" mysql
run apt-key adv --keyserver keys.gnupg.net --recv-keys 1C4CBDCDCD2EFD2A
run echo "deb http://repo.percona.com/apt trusty main" >> /etc/apt/sources.list && \
    echo "deb-src http://repo.percona.com/apt trusty main" >> /etc/apt/sources.list
run mkdir -p /var/run/mysqld
run apt-get update && DEBIAN_FRONTEND noninteractive apt-get -qy install percona-server-server-5.5 percona-server-client-5.5

add my.cnf /etc/mysql/my.cnf

volume /dbdata

expose 3306

cmd /usr/bin/mysqld_safe
