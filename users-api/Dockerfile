FROM openjdk:8-alpine as stage1
WORKDIR /src
COPY . .
RUN chmod 777 mvnw
RUN ./mvnw clean install

FROM openjdk:8-alpine
EXPOSE 8083
COPY --from=stage1 /src/target/users-api-0.0.1-SNAPSHOT.jar users-api.jar
ENV JWT_SECRET=PRFT
ENV SERVER_PORT=8083
ENV ZIPKIN_URL=http://zipkin:9411
ENTRYPOINT ["java", "-jar", "/users-api.jar"]