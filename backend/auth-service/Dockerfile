FROM maven:3.8.5-openjdk-17

COPY . /auth-service/
WORKDIR /auth-service/

RUN mvn clean install -DskipTests
EXPOSE 9001

ENTRYPOINT ["java", "-jar", "target/auth-service-0.0.1-SNAPSHOT.jar"]
