FROM alpine:3.9
LABEL maintainer="leejc1994@gmail.com"
##RUN apk update && apk upgrade



RUN apk --no-cache add ca-certificates tzdata && \
    cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    wget -q -O /etc/apk/keys/sgerrand.rsa.pub https://alpine-pkgs.sgerrand.com/sgerrand.rsa.pub && \
    wget https://github.com/sgerrand/alpine-pkg-glibc/releases/download/2.29-r0/glibc-2.29-r0.apk && \
    apk add glibc-2.29-r0.apk && \
    rm -rf glibc-2.29-r0.apk && \
    wget --no-check-certificate \
    --header "Cookie: oraclelicense=accept-securebackup-cookie" \
    -P /usr/local/ \
    https://download.oracle.com/otn-pub/java/jdk/8u201-b09/42970487e3af4f5aa5bca3f542482c60/jre-8u201-linux-x64.tar.gz && \
    tar -xzf /usr/local/jre-8u201-linux-x64.tar.gz -C /usr/local/ && \
    rm -rf /usr/local/jre-8u201-linux-x64.tar.gz

ENV JAVA_HOME=/usr/local/jre1.8.0_201
ENV PATH=${JAVA_HOME}/bin:$PATH
ENV CLASSPATH=.:${JAVA_HOME}/lib
ENV LANG=zh_CN.UTF-8
