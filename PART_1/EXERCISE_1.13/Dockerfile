FROM golang:1.16.15

WORKDIR /usr/src/app

COPY . .

RUN go build

ENV PORT=8080
ENV REQUEST_ORIGIN=https://example.com

EXPOSE ${PORT}

RUN chmod +x ./server
RUN go test ./...

CMD ./server
