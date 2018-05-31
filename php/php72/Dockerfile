FROM php:7.2-fpm

COPY ./sources.list.stretch /etc/apt/sources.list

# Extensions: ctype, dom, fileinfo, ftp, hash, iconv, json, pdo, pdo_sqlite, session,
# tokenizer, simplexml, xml, xmlreader, xmlwriter and phar are bundled and compiled into
# PHP by default. If missing, install them directly by `docker-php-ext-install extension_name`

# Notice:
# 1. Mcrypt was DEPRECATED in PHP 7.1.0, and REMOVED in PHP 7.2.0.
# 2. opcache requires PHP version >= 7.0.0.
# 3. soap requires libxml2-dev.
# 4. xml, xmlrpc, wddx require libxml2-dev and libxslt-dev.
# 5. Line `&& :\` is just for better reading and do nothing.
RUN yum update \
    && yum install -y libfreetype6-dev libjpeg62-turbo-dev libpng-dev \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install gd \
    && :\
    && yum install -y libicu-dev \
    && docker-php-ext-install intl \
    && :\
    && yum install -y libxml2-dev \
    && yum install -y libxslt-dev \
    && docker-php-ext-install soap \
    && docker-php-ext-install xsl \
    && docker-php-ext-install xmlrpc \
    && docker-php-ext-install wddx \
    && :\
    && yum install -y libbz2-dev \
    && docker-php-ext-install bz2 \
    && :\
    && docker-php-ext-install zip \
    && docker-php-ext-install pcntl \
    && docker-php-ext-install pdo_mysql \
    && docker-php-ext-install mysqli \
    && docker-php-ext-install mbstring \
    && docker-php-ext-install exif \
    && docker-php-ext-install bcmath \
    && docker-php-ext-install calendar \
    && docker-php-ext-install sockets \
    && docker-php-ext-install gettext \
    && docker-php-ext-install shmop \
    && docker-php-ext-install sysvmsg \
    && docker-php-ext-install sysvsem \
    && docker-php-ext-install sysvshm \
    && docker-php-ext-install opcache
    #&& docker-php-ext-install pdo_firebird \
    #&& docker-php-ext-install pdo_dblib \
    #&& docker-php-ext-install pdo_oci \
    #&& docker-php-ext-install pdo_odbc \
    #&& docker-php-ext-install pdo_pgsql \
    #&& docker-php-ext-install pgsql \
    #&& docker-php-ext-install oci8 \
    #&& docker-php-ext-install odbc \
    #&& docker-php-ext-install dba \
    #&& docker-php-ext-install interbase \
    #&& :\
    #&& yum install -y libmcrypt-dev \
    #&& docker-php-ext-install mcrypt \
    #&& :\
    #&& yum install -y curl \
    #&& yum install -y libcurl3 \
    #&& yum install -y libcurl4-openssl-dev \
    #&& docker-php-ext-install curl \
    #&& :\
    #&& yum install -y libreadline-dev \
    #&& docker-php-ext-install readline \
    #&& :\
    #&& yum install -y libsnmp-dev \
    #&& yum install -y snmp \
    #&& docker-php-ext-install snmp \
    #&& :\
    #&& yum install -y libpspell-dev \
    #&& yum install -y aspell-en \
    #&& docker-php-ext-install pspell \
    #&& :\
    #&& yum install -y librecode0 \
    #&& yum install -y librecode-dev \
    #&& docker-php-ext-install recode \
    #&& :\
    #&& yum install -y libtidy-dev \
    #&& docker-php-ext-install tidy \
    #&& :\
    #&& yum install -y libgmp-dev \
    #&& ln -s /usr/include/x86_64-linux-gnu/gmp.h /usr/include/gmp.h \
    #&& docker-php-ext-install gmp \
    #&& :\
    #&& yum install -y postgresql-client \
    #&& yum install -y mysql-client \
    #&& :\
    #&& yum install -y libc-client-dev \
    #&& docker-php-ext-configure imap --with-kerberos --with-imap-ssl \
    #&& docker-php-ext-install imap \
    #&& :\
    #&& yum install -y libldb-dev \
    #&& yum install -y libldap2-dev \
    #&& docker-php-ext-configure ldap --with-libdir=lib/x86_64-linux-gnu \
    #&& docker-php-ext-install ldap \

# Composer
#RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin/ --filename=composer \
