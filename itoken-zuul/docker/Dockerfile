FROM openjdk:8-jre

MAINTAINER QJB<954566097@qq.com>

ENV DOCKERIZE_VERSION v0.6.1

RUN wget https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && tar -C /usr/local/bin -xzvf dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && rm dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz

RUN mkdir /app

COPY itoken-zuul-1.0.0-SNAPSHOT.jar /app/app.jar

ENTRYPOINT ["dockerize", "-timeout", "5m", "-wait", "http://192.168.114.131:8761","java","-Djava.security.egd=file:/dev/./urandom","-jar","/app/app.jar","--spring.profiles.active=prod"]

EXPOSE 8769