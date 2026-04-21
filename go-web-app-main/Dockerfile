FROM golang:1.26.2-alpine3.22 AS builder

WORKDIR /app

COPY go.mod .

#Installing dependencies form go.mod file

RUN go mod download 

COPY . .

#RUN application in /app directory

RUN go build -o main .


FROM gcr.io/distroless/static-debian12

COPY --from=builder /app/main .

COPY --from=builder /app/static ./static

EXPOSE 8080

CMD ["./main"]
