FROM golang:1.18.2-alpine

WORKDIR /usr/src/app

COPY . .

ENV JWT_SECRET=PRFT 
ENV AUTH_API_PORT=9000 
ENV USERS_API_ADDRESS=http://users-api:8083 

RUN export GO111MODULE=on
RUN go mod init github.com/bortizf/microservice-app-example/tree/master/auth-api
RUN go mod tidy
RUN go build -v -o /usr/local/bin/app ./...

EXPOSE 9000

CMD ["app"]
