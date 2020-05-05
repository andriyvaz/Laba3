FROM maven:3.6.3-jdk-11-slim AS builder
COPY . /
WORKDIR /
RUN mvn clean package -Dmaven.test.skip=true
FROM openjdk:8-jre-alpine
COPY --from=builder /target/ROOT.jar /
ENTRYPOINT java -jar ROOT.jar

