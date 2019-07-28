# grpc-demo

#COMPARISON GRPC HTTP-REST
https://docs.microsoft.com/en-us/aspnet/core/grpc/comparison?view=aspnetcore-3.0

Performance : https://husobee.github.io/golang/rest/grpc/2016/05/28/golang-rest-v-grpc.html

HTTP2 vs HTTP1.1 : https://imagekit.io/demo/http2-vs-http1

#INSTALL PROTOC

##Mac
brew install protobuf

##Windows

- Download from https://github.com/google/protobuf/releases:
example:
https://github.com/protocolbuffers/protobuf/releases/download/v3.9.0/protoc-3.9.0-win64.zip
- Extract
- Add to path

##HOW-TO
protoc <FILE>.proto --java_out=<GEN_PATH>
