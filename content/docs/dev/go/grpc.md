---
title: "Grpc使用"
weight: 4
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: true
---

<!--more-->

## Install
1. Install [protoc](https://github.com/protocolbuffers/protobuf/releases)
```bash
wget https://github.com/protocolbuffers/protobuf/releases/download/v3.13.0/protoc-3.13.0-linux-x86_64.zip
unzip protoc-3.13.0-linux-x86_64.zip -d /usr/local/protoc
export PATH=$PATH:/usr/local/protoc/bin
source ~/.bashrc
```
2. Download `protoc-gen-go`
```bash
go get -u github.com/golang/protobuf/protoc-gen-go
go install $GOPATH/src/github.com/golang/protobuf/protoc-gen-go
```

## Usage
1. Create `*.proto` file
```grpc
// Specify syntax format, note that proto3 no supports required and optimal in proto2 anymore
syntax = "proto3";

// Specifies the package name of the generated *.pb.go
package grpc;

// Specifies the package path of the generated *.pb.go package
option go_package = ".;grpc";

// Service defines the service called by the development
service DemoService {
    rpc DemoReq(DemoRequest) returns (DemoResponse) {}
}

message DemoRequest{
    uint32 Id = 1;
    string Name = 2;
}

message DemoResponse{
}
```
2. Generate
```bash
protoc -I . --go_out=plugins=grpc:. ./*.proto
```
