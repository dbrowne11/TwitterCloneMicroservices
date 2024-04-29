FROM maven:3.8.5-openjdk-17

COPY . /config-server/
WORKDIR /config-server/

RUN mvn clean install -DskipTests
EXPOSE 9296

# ARG JAR_FILE=target/*.jar
# CMD ["sleep", "3600"]
ENTRYPOINT ["java", "-jar", "target/config-server-0.0.1-SNAPSHOT.jar"]