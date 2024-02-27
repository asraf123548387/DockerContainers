FROM openjdk:17
WORKDIR /app
COPY target/Home-0.0.1-SNAPSHOT.jar /app/demo.jar
EXPOSE  8080
RUN wget https://github.com/jwilder/dockerize/releases/download/v0.6.1/dockerize-linux-amd64-v0.6.1.tar.gz \
    && tar -C /usr/local/bin -xzvf dockerize-linux-amd64-v0.6.1.tar.gz \
    && rm dockerize-linux-amd64-v0.6.1.tar.gz
CMD dockerize -wait tcp://db:3306 -timeout  1m java -jar /app/demo.jar
