FROM golang:1.22-alpine AS build
WORKDIR /app
COPY . .
RUN go mod init app2 && go get github.com/gin-gonic/gin && go build -o app2

FROM alpine
WORKDIR /app
COPY --from=build /app/app2 .
EXPOSE 80
CMD ["./app2"]
