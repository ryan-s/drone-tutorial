# Multi-stage build form
FROM golang:latest

# Copy in code...
RUN mkdir -p /go/src/github.com/josebarn/drone-tutorial
ADD main.go /go/src/github.com/josebarn/drone-tutorial/
ADD api/ /go/src/github.com/josebarn/drone-tutorial/api/
ADD model/ /go/src/github.com/josebarn/drone-tutorial/model/
ADD vendor/ /go/src/github.com/josebarn/drone-tutorial/vendor/

RUN ls -laR

# Build app
WORKDIR /go/src/github.com/josebarn/drone-tutorial
RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o hello-world .

# Could use something even smaller...
FROM alpine:latest
RUN apk --no-cache add ca-certificates

RUN mkdir /app
WORKDIR /app/
COPY --from=0 /go/src/github.com/josebarn/drone-tutorial/hello-world .

# Expose ports for future REST Interface
EXPOSE 8080

CMD ["/app/hello-world"]
