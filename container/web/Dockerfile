# CentOS 7
FROM centos:7

RUN yum update -y && yum clean all

# EPEL
RUN yum install -y epel-release
# remi
RUN yum -y install http://rpms.famillecollet.com/enterprise/remi-release-7.rpm

# Apache sudo curl
RUN yum install -y httpd sudo curl

# PHP
RUN yum -y install --enablerepo=remi,remi-php74 php php-devel php-mbstring php-pdo php-xml php-gd php-fpm php-mysqlnd php-opcache php-pecl-zip libzip5

# Node.js
RUN curl -sL https://rpm.nodesource.com/setup_14.x | sudo bash -
RUN yum -y install nodejs

WORKDIR /var/www/html

EXPOSE 80

ENTRYPOINT ["/usr/sbin/httpd", "-DFOREGROUND"]
