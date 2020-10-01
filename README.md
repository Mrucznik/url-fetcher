# Fetcher API

This is simple fetcher API, which provides service for saving URLs and getting data from it with specified time interval.

## How to build
You need the Google protocol buffers compiler to build this project. You can download it from the official repository: https://github.com/protocolbuffers/protobuf/releases 
```
$ go install \
      github.com/grpc-ecosystem/grpc-gateway/protoc-gen-grpc-gateway \
      github.com/grpc-ecosystem/grpc-gateway/protoc-gen-swagger \
      github.com/golang/protobuf/protoc-gen-go
$ go generate
$ go build .
```

## How to run

#### Normal way
```
$ go run .
```
#### With docker
```
$ docker-compose up
```

## Configuration

You can configure this project by setting up environment variables:
- PORT - port on which HTTP server will be listening on.
- GRPC_PORT - port on which gRPC server will be listening on.

## Project structure

- db - contains database schema
- engine - contains source code of saving URLs and fetching mechanism
    - database - implementation with storing URLs in database
    - in_memory - implementation with storing URLs in memory
- grpc - contains gRPC API server with gRPC gateway
    - proto - protobuf files
    - third_party - third party files
- rest - contains HTTP API server with Chi router
