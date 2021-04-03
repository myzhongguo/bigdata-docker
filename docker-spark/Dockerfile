FROM tonywell/docker-hive

MAINTAINER tonywell <tongwei1985@gmail.com>

ENV SPARK_HOME=/usr/local/spark
ENV PATH=$PATH:$SPARK_HOME/bin:$SPARK_HOME/sbin:.

ENV JAVA_HOME /usr/local/jdk1.8
ENV PATH $JAVA_HOME/bin:$PATH

RUN wget https://mirrors.tuna.tsinghua.edu.cn/apache/spark/spark-3.1.1/spark-3.1.1-bin-without-hadoop.tgz && \
    tar -xzvf spark-3.1.1-bin-without-hadoop.tgz -C /usr/local/ && \
    mv /usr/local/spark-3.1.1-bin-without-hadoop /usr/local/spark && \
    rm -rf spark-3.1.1-bin-without-hadoop.tgz
