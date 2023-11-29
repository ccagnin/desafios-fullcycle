FROM golang:1.16.3-alpine3.13 AS builder

WORKDIR /app

COPY . .

RUN CGO_ENABLED=0 GOOS=linux go build -o main .

FROM scratch

WORKDIR /app

COPY --from=builder /app/main /app/

CMD ["./main"]

