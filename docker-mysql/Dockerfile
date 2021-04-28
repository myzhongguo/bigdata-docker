## 原生mysql镜像制作
#FROM centos:7
#MAINTAINER yun
#WORKDIR /opt/software
#RUN yum -y update && \
#    yum -y install wget ncurses ncurses-devel bison cmake make gcc gcc-c++ zlib-devel  openssl openssl-devel && \
#    groupadd mysql && \
#    useradd -M -s /sbin/nologin mysql -g mysql
#RUN wget https://nchc.dl.sourceforge.net/project/boost/boost/1.59.0/boost_1_59_0.tar.gz && \
#    tar -zvxf boost_1_59_0.tar.gz
##源码安装mysql
#RUN wget http://mypicbed.top:8020/mysql/mysql-5.7.20.tar.gz && \
#    tar -zxvf mysql-5.7.20.tar.gz -C /opt/software/ && \
#    mv boost_1_59_0 /opt/software/mysql-5.7.20/boost && \
#    rm mysql-5.7.20.tar.gz
#
#RUN cd /opt/software/mysql-5.7.20 && \
#    cmake \
#    -DCMAKE_INSTALL_PREFIX=/usr/local/mysql \
#    -DMYSQL_UNIX_ADDR=/usr/local/mysql/mysql.sock \
#    -DSYSCONFDIR=/etc \
#    -DSYSTEMD_PID_DIR=/usr/local/mysql \
#    -DDEFAULT_CHARSET=utf8  \
#    -DDEFAULT_COLLATION=utf8_general_ci \
#    -DWITH_INNOBASE_STORAGE_ENGINE=1 \
#    -DWITH_ARCHIVE_STORAGE_ENGINE=1 \
#    -DWITH_BLACKHOLE_STORAGE_ENGINE=1 \
#    -DWITH_PERFSCHEMA_STORAGE_ENGINE=1 \
#    -DMYSQL_DATADIR=/usr/local/mysql/data \
#    -DWITH_BOOST=boost \
#    -DWITH_SYSTEMD=1 && make && make install
#RUN  cd ../ && rm -rf /opt/software/mysql-5.7.20 && chown -R mysql:mysql /usr/local/mysql && rm -rf /etc/my.cnf
#ADD my.cnf /etc/my.cnf
#RUN chown mysql:mysql /etc/my.cnf
#ENV PATH $PATH:/usr/local/mysql/bin:/usr/local/mysql/lib
#RUN /usr/local/mysql/bin/mysqld --initialize-insecure --user=mysql --basedir=/usr/local/mysql --datadir=/usr/local/mysql/data
#ENV MYSQL_HOME /usr/local/mysql
## 容器需要开放MySQL 3306端口
#EXPOSE 3306
#ADD mysqld.service /usr/lib/systemd/system/
#RUN echo -e "#!/bin/sh	\nsystemctl enable mysqld" > /run.sh && chmod 0644 /usr/lib/systemd/system/mysqld.service && chmod 755 /run.sh
#RUN sh /run.sh
#CMD ["/usr/sbin/init"]

## from官方镜像制作

FROM mysql:5.7.24
# 维护者信息
MAINTAINER liu

# 设置root初始化密码
ENV MYSQL_ROOT_PASSWORD=123456
# 设置mysql字符集
ADD my.cnf /etc/mysql/mysql.conf.d/my.cnf

EXPOSE 3306