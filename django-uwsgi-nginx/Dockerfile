from ubuntu:14.04
maintainer mrpaws <paws@delimitize.com>

# env/application parameters
env VIRTUAL_ENV /var/env
env PROJECT_NAME app
env PATH /var/env/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin

run useradd -rR ${VIRTUAL_ENV} -s /bin/false -c "django env owner" app
run apt-get update 
run DEBIAN_FRONTEND=noninteractive apt-get install -qy zsh python build-essential python-mysqldb python-dev python-pip 
run pip install virtualenv==1.11.6

# prepare environment
run virtualenv ${VIRTUAL_ENV}
WORKDIR /var/env

run pip install uwsgi==2.0.6
run pip install django==1.6.5
run chown -R appman:appman ${VIRTUAL_ENV}

# insert volume add/git pull, dir add, etc

run zsh [[ -e ${VIRTUAL_ENV}/${PROJECT_NAME} ]] || python bin/django-admin.py startproject ${PROJECT_NAME} ${VIRTUAL_ENV}
