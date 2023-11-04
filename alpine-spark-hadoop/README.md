# Dockerfile Documentation

<div align="center">

![Docker](https://img.shields.io/badge/-Docker-black?style=flat-square&logo=docker)
![Alpine](https://img.shields.io/badge/-Alpine-black?style=flat-square&logo=alpine-linux)
![curl](https://img.shields.io/badge/-curl-black?style=flat-square&logo=curl)
![Git](https://img.shields.io/badge/-Git-black?style=flat-square&logo=git)
![Java](https://img.shields.io/badge/-Java-black?style=flat-square&logo=java)
![Maven](https://img.shields.io/badge/-Maven-black?style=flat-square&logo=apache-maven)
![Bash](https://img.shields.io/badge/-Bash-black?style=flat-square&logo=gnu-bash)
![Apache Spark](https://img.shields.io/badge/-Apache%20Spark-black?style=flat-square&logo=apache-spark)
![Apache Hadoop](https://img.shields.io/badge/-Apache%20Hadoop-black?style=flat-square&logo=apache-hadoop)

</div>

## Overview

This Dockerfile is used to create a Docker image with the following components:

- Alpine: A lightweight Linux distribution.
- curl, git, openjdk11, maven, bash: These tools are installed using the apk package manager.
- Apache Spark: An open-source distributed general-purpose cluster-computing framework. The version installed is specified by the `SPARK_VERSION` environment variable.
- Apache Hadoop: A collection of open-source software utilities that facilitate using a network of many computers to solve problems involving massive amounts of data and computation. The version installed is specified by the `HADOOP_VERSION` environment variable.

## Dockerfile Breakdown

1. The base image is Alpine.
2. It updates the existing packages, upgrades them if necessary, and installs curl, git, openjdk11, maven, and bash.
3. It sets environment variables for the versions of Spark and Hadoop, as well as their package names and installation directories.
4. It downloads and installs Spark and Hadoop from the official Apache download site.
5. It exposes port 4040, which is the default port for the Spark web UI.

## Usage

To build a Docker image from this Dockerfile, navigate to the directory containing the Dockerfile and run the following command:

```bash
docker build -t my-spark-hadoop-image .
```

To run a container from this image, use the following command:

```bash
docker run -it -p 4040:4040 my-spark-hadoop-image /bin/bash
```
