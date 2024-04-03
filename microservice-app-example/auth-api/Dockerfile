FROM golang:1.9-alpine

WORKDIR /go/src/app

EXPOSE 8000

RUN apk --no-cache add curl git && \
    curl https://raw.githubusercontent.com/golang/dep/master/install.sh | sh

COPY . .

RUN dep ensure

RUN go build -o auth-api

CMD /go/src/app/auth-api