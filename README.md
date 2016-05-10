#Apache Hadoop 2.6.0 Docker image

Forked from [SequenceIQ](https://github.com/sequenceiq/docker-hadoop).

# Build the image

If you'd like to try directly from the Dockerfile you can build the image as:

```
docker build  -t bernieai/docker-hadoop:2.6.0 .
```
# Pull the image

The image is also released as an official Docker image from Docker's automated build repository - you can always pull or refer the image when launching containers.

```
docker pull bernieai/docker-hadoop:2.6.0
```

# Start a container

In order to use the Docker image you have just build or pulled use:

```
docker run -i -t bernieai/docker-hadoop:2.6.0 /etc/bootstrap.sh -bash
```

## Testing

You can run one of the stock examples:

```
cd $HADOOP_PREFIX
# run the mapreduce
bin/hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-2.6.0.jar grep input output 'dfs[a-z.]+'

# check the output
bin/hdfs dfs -cat output/*
```

## Hadoop native libraries, build, Bintray, etc

The Hadoop build process is no easy task - requires lots of libraries and their right version, protobuf, etc and takes some time - SequenceIQ has simplified all these, made the build and released a 64b version of Hadoop nativelibs on this [Bintray repo](https://bintray.com/sequenceiq/sequenceiq-bin/hadoop-native-64bit/2.5.0/view/files). Enjoy.

## Automate everything

Docker file is available in the official [Docker repository](https://registry.hub.docker.com/u/bernieai/docker-hadoop/).
