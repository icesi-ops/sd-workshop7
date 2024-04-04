FROM golang:1.18.2-alpine as stage1
WORKDIR /src
COPY Gopkg.* *.go .
RUN export GO111MODULE=on
RUN go mod init github.com/bortizf/microservice-app-example/tree/master/auth-api
RUN go mod tidy
RUN go build -o ./auth-api

FROM golang:1.18.2-alpine
EXPOSE 8000
COPY --from=stage1 /src/auth-api /auth-api
ENV JWT_SECRET=PRFT
ENV AUTH_API_PORT=8000
ENV USERS_API_ADDRESS=http://users-api:8083
ENV ZIPKIN_URL=http://zipkin:9411
ENTRYPOINT ["/auth-api"]