FROM centos:6

RUN yum update -y \
    && yum upgrade -y \
    && yum install -y wget \
                      httpd \
                      mod_ssl \
                      php \
                      php-dom \
                      php-gd \
                      php-mbstring \
                      php-mcrypt \
                      php-mysql \
                      php-mysqli \
                      php-pdo \
                      php-sqlite \
                      php-wddx \
                      php-xml \
                      php-xsl \
    && echo "see https://stackoverflow.com/questions/17109818/install-php-mcrypt-on-centos-6" \
    && wget -q http://dl.fedoraproject.org/pub/epel/6/x86_64/epel-release-6-8.noarch.rpm \
    && wget -q http://rpms.famillecollet.com/enterprise/remi-release-6.rpm \
    && rpm -Uvh remi-release-6*.rpm epel-release-6*.rpm \
    && yum update -y \
    && yum install -y php-mcrypt* \
    && rm remi-release-6*.rpm epel-release-6*.rpm

WORKDIR /etc/httpd

EXPOSE 80 443
CMD ["httpd"]
