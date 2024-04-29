FROM maven:3.8.5-openjdk-17

COPY . /reply-service/
WORKDIR /reply-service/
RUN ls
RUN mvn clean install -DskipTests
EXPOSE 9003
ENTRYPOINT ["java", "-jar", "target/reply-service-0.0.1-SNAPSHOT.jar"]
