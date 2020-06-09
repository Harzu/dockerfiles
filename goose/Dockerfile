FROM golang:alpine as builder

RUN apk add --no-cache git ca-certificates build-base

RUN PATH=${PATH}:${GOPATH}
RUN go get -u github.com/pressly/goose/cmd/goose

RUN cp ${GOPATH}/bin/goose /bin/goose

ENTRYPOINT []

FROM alpine as goose
COPY --from=builder /bin/goose /bin/goose
WORKDIR /goose