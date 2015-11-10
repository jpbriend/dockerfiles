FROM gettyimages/spark:1.5.1-hadoop-2.6

MAINTAINER Ogury Team <it@ogury.co>

ENV SBT_VERSION 0.13.8
ENV SBT_HOME /usr/local/sbt
ENV PATH ${PATH}:${SBT_HOME}/bin

WORKDIR /opt

# INSTALL SBT
RUN curl -sL "http://dl.bintray.com/sbt/native-packages/sbt/$SBT_VERSION/sbt-$SBT_VERSION.tgz" | gunzip | tar -x -C /usr/local && \
    echo -ne "- with sbt $SBT_VERSION\n" >> /root/.built

RUN sbt sbtVersion && \
    mkdir /workdir

WORKDIR /workdir

CMD ["sbt", "clean test package"]
