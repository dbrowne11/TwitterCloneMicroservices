FROM maven:3.8.5-openjdk-17

COPY . /tweet-service/
WORKDIR /tweet-service/

RUN mvn install -DskipTests
EXPOSE 9002

ENTRYPOINT ["java", "-jar", "target/tweet-service-0.0.1-SNAPSHOT.jar"]

