FROM maven:3.8.5-openjdk-17

COPY . /cloud-gateway/
WORKDIR /cloud-gateway/

RUN mvn clean install -DskipTests
EXPOSE 9090


ENTRYPOINT ["java", "-jar", "target/cloud-gateway-0.0.1-SNAPSHOT.jar"]

