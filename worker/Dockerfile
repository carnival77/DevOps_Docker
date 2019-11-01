FROM maven:3.5-jdk-8-alpine AS builder
COPY . /usr/src/app
WORKDIR /usr/src/app
RUN mvn dependency:resolve
RUN mvn package

FROM openjdk:8-jre-alpine
COPY --from=builder /usr/src/app/target/worker-jar-with-dependencies.jar .
CMD java -jar worker-jar-with-dependencies.jar