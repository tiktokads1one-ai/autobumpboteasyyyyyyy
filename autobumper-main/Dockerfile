FROM golang:1.21-alpine AS builder

WORKDIR /app
COPY . .

RUN go build -tags netgo -ldflags '-s -w' -o app

FROM alpine:latest

WORKDIR /app
COPY --from=builder /app/app .

CMD ["./app"]
