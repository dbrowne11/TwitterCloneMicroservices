FROM maven:3.8.5-openjdk-17

COPY . /service-registry/
WORKDIR /service-registry/

RUN mvn install -DskipTests
EXPOSE 8761

ENTRYPOINT ["java", "-jar", "target/service-registry-0.0.1-SNAPSHOT.jar"]

