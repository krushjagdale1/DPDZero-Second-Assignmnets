FROM golang:1.20

WORKDIR /app

COPY . .

RUN go mod init app && go build -o main .

EXPOSE 8001

CMD ["./main"]

