FROM tonywell/docker-hadoop

MAINTAINER tonywell <tongwei1985@gmail.com>

ENV HIVE_HOME=/usr/local/hive

RUN wget https://mirrors.bfsu.edu.cn/apache/hive/hive-3.1.2/apache-hive-3.1.2-bin.tar.gz && \
     tar -zvxf apache-hive-3.1.2-bin.tar.gz -C /usr/local/ && \
     mv /usr/local/apache-hive-3.1.2-bin /usr/local/hive && \
     rm apache-hive-3.1.2-bin.tar.gz

RUN wget http://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.39.tar.gz && \
    tar -zvxf mysql-connector-java-5.1.39.tar.gz -C /usr/local/ && \
    mv /usr/local/mysql-connector-java-5.1.39/mysql-connector-java-5.1.39-bin.jar $HIVE_HOME/lib/ && \
    rm -rf /usr/local/mysql-connector-java-5.1.39 

RUN mkdir -p /usr/hive/warehouse && mkdir -p /usr/hive/log

ENV PATH=$PATH:$HIVE_HOME/bin:.

 
     
