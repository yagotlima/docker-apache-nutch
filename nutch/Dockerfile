FROM yagotlima/apache-ant:1.10.5

ARG NUTCH_VERSION=2.3.1

LABEL maintainer="Yago Lima <yagotoledolima@gmail.com>"

ENV NUTCH_JAVA_HOME=$JAVA_HOME

RUN apt-get update && \
	apt-get install -y bash

WORKDIR /opt

RUN wget http://mirror.nbtelecom.com.br/apache/nutch/$NUTCH_VERSION/apache-nutch-$NUTCH_VERSION-src.zip && \
    wget https://apache.org/dist/nutch/$NUTCH_VERSION/apache-nutch-$NUTCH_VERSION-src.zip.sha512 && \ 
    echo -n "`cat apache-nutch-$NUTCH_VERSION-src.zip.sha512 | cut -d " " -f 2`  apache-nutch-$NUTCH_VERSION-src.zip" | sha512sum -c && \
    unzip apache-nutch-$NUTCH_VERSION-src.zip && \
    rm apache-nutch-$NUTCH_VERSION-src.zip apache-nutch-$NUTCH_VERSION-src.zip.sha512 && \
    mv apache-nutch-$NUTCH_VERSION apache-nutch

WORKDIR /opt/apache-nutch

#RUN rm -fr conf
#COPY conf conf

#RUN ant runtime
