#1 
FROM golang:1.16 as builder
WORKDIR /app
COPY go.mod .
RUN go mod download
COPY main.go .
RUN go build -o main .

#2
FROM alpine:latest
WORKDIR /root/
COPY --from=builder /app/main .
CMD ["./main"]
