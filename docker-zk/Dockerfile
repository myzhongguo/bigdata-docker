FROM tonywell/centos-java

RUN wget http://archive.apache.org/dist/zookeeper/zookeeper-3.6.2/apache-zookeeper-3.6.2-bin.tar.gz && \
      tar -zvxf apache-zookeeper-3.6.2-bin.tar.gz -C /opt/ && \
      mv /opt/apache-zookeeper-3.6.2-bin /opt/zookeeper && \
      rm apache-zookeeper-3.6.2-bin.tar.gz

RUN mkdir -p /opt/data
RUN mkdir -p /opt/log

ENV ZOO_HOME /opt/zookeeper
ENV PATH $PATH:$ZOO_HOME/bin

ENV TZ "Asia/Shanghai"
EXPOSE 2181 2888 3888
CMD ["zkServer.sh", "start-foreground"]
