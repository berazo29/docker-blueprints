FROM alpine

RUN apk update && apk upgrade && apk add --no-cache curl git openjdk11 maven bash
ENV SPARK_VERSION=3.4.1
ENV HADOOP_VERSION=3.3.6
ENV SPARK_PACKAGE=spark-${SPARK_VERSION}-bin-hadoop3 \
    SPARK_HOME=/opt/spark-${SPARK_VERSION} \
    HADOOP_PACKAGE=hadoop-${HADOOP_VERSION} \
    HADOOP_HOME=/opt/hadoop-${HADOOP_VERSION}

RUN curl -sL --retry 3 https://dlcdn.apache.org/spark/spark-${SPARK_VERSION}/${SPARK_PACKAGE}.tgz | gunzip | tar -x -C /opt/ && mv /opt/${SPARK_PACKAGE} ${SPARK_HOME}
RUN curl -sL --retry 3 https://dlcdn.apache.org/hadoop/common/hadoop-${HADOOP_VERSION}/${HADOOP_PACKAGE}.tar.gz | gunzip | tar -x -C /opt/

EXPOSE 4040