# build container
FROM golang:1.27-bookworm AS builder

WORKDIR /src

COPY go.* .
COPY main.go .

# build file in /src/app
RUN  CGO_ENABLED=0 go build -o app .
# get a binary file app

# run container
FROM debian:bookworm

WORKDIR /app

# copying the build file to run container
COPY public public
COPY templates templates
COPY --from=builder /src/app .

ENV PORT="3000"
ENV INSTANCE_NAME="dov-bear"
ENV INSTANCE_NAME="1234"

EXPOSE ${PORT}

SHELL ["/bin/sh", "-c"]
ENTRYPOINT ./app