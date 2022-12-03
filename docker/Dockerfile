FROM maven:3-jdk-11 AS MAVEN_BUILD
## создаем jar
RUN mkdir -p /tmp/code; mkdir -p /pfb
COPY ../* /tmp/code/

WORKDIR /tmp/code/
RUN mvn clean; mvn test; mvn -DskipTests package

RUN cp /tmp/code/target/pfb-0.1.0.jar /pfb/pfb.jar
RUN rm -rf /tmp/code

FROM openjdk:11-jdk-slim
## переходим в рабочую папку для запуска приложения
WORKDIR /pfb
#ENTRYPOINT ["java","-jar","pfb.jar"]
ENTRYPOINT ["ls"]

EXPOSE "8080"