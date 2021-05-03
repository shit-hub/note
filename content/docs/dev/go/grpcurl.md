---
title: "安装Grpcurl"
weight: 5
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: true
---

<!--more-->

Environment:
- System: linux
- Go: 1.13+
## Install
1. Install dependent package
```bash
mkdir -p $GOPATH/src/google.golang.org
git clone https://github.com/protocolbuffers/protobuf-go.git $GOPATH/src/google.golang.org/protobuf
git clone https://github.com/googleapis/go-genproto.git $GOPATH/src/google.golang.org/genproto
git clone https://github.com/grpc/grpc-go.git $GOPATH/src/google.golang.org/grpc
git clone https://github.com/golang/net.git $GOPATH/src/golang.org/x/net
git clone https://github.com/golang/sys.git $GOPATH/src/golang.org/x/sys
git clone https://github.com/golang/text.git $GOPATH/src/golang.org/x/text
```
2. Download grpcurl
```bash
go get github.com/fullstorydev/grpcurl
```
3. Install
```bash
go install $GOPATH/src/github.com/fullstorydev/grpcurl/cmd/grpcurl
```
> if tips no dependent package, go to `$GOPATH/src/github.com/fullstorydev/grpcurl/` to run `go build ./cmd/grpcurl`
