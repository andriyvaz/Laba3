FROM maven:3.6.3-jdk-11-slim AS builder
COPY . /footgo
WORKDIR /footgo
RUN mvn clean package -Dmaven.test.skip=true
FROM openjdk:8-jre-alpine
COPY --from=builder /footgo/target/ROOT.jar /
EXPOSE 8080
ENTRYPOINT java -jar ROOT.jar

