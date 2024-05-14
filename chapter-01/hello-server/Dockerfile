FROM golang:1.22 AS builder

WORKDIR /app
COPY main.go main.go
COPY go.mod go.mod
ENV CGO_ENABLED=0
RUN go build -o hello .

FROM scratch
COPY --from=builder /app/hello /hello
ENTRYPOINT [ "/hello" ]