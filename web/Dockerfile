FROM golang:onbuild
WORKDIR /go/src/github.com/MosHelper/golang_exsample
COPY . .
RUN go get github.com/kataras/iris
RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o main .

FROM alpine:latest  
RUN apk --no-cache add ca-certificates
# WORKDIR /root/
# COPY --from=0 /go/src/github.com/MosHelper/golang_exsample .
# COPY /go/src/github.com/MosHelper/golang_exsample .
CMD ["./main"]  

