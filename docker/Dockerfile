FROM openjdk:8-jre

RUN wget https://github.com/jwilder/dockerize/releases/download/v0.6.1/dockerize-linux-amd64-v0.6.1.tar.gz \
    && tar -C /usr/local/bin -xzvf dockerize-linux-amd64-v0.6.1.tar.gz \
    && rm dockerize-linux-amd64-v0.6.1.tar.gz

RUN mkdir /app

COPY jiang-admin-1.0.0-SNAPSHOT.jar /app/

ENTRYPOINT ["dockerize", "-timeout", "5m", "-wait", "http://104.199.166.17:8888/jiang-admin/dev/master", "java", "-Djava.security.egd=file:/dev/./urandom", "-jar", "/app/jiang-admin-1.0.0-SNAPSHOT.jar"]


EXPOSE 8084