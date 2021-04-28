FROM tonywell/centos-java
MAINTAINER tonywell

RUN yum -y install which && yum clean all

#下载Hadoop
RUN wget https://mirrors.tuna.tsinghua.edu.cn/apache/hadoop/common/hadoop-3.2.2/hadoop-3.2.2.tar.gz && \
        tar -zvxf hadoop-3.2.2.tar.gz -C /usr/local/ && \
        mv /usr/local/hadoop-3.2.2 /usr/local/hadoop && \
        rm -rf hadoop-3.2.2.tar.gz && ln -s /usr/local/hadoop/etc/hadoop /etc/hadoop

ENV HADOOP_HOME /usr/local/hadoop
ENV HADOOP_PREFIX /usr/local/hadoop
ENV HADOOP_COMMON_HOME /usr/local/hadoop
ENV HADOOP_HDFS_HOME /usr/local/hadoop
ENV HADOOP_MAPRED_HOME /usr/local/hadoop
ENV HADOOP_YARN_HOME /usr/local/hadoop
ENV HADOOP_CONF_DIR /usr/local/hadoop/etc/hadoop
#ENV YARN_CONF_DIR $HADOOP_PREFIX/etc/hadoop
ENV YARN_CONF_DIR /usr/local/hadoop/etc/hadoop
ENV PATH $HADOOP_HOME/bin:$PATH
