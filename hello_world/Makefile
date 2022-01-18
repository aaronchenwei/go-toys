.PHONY: all build clean run check cover lint docker help

BINARY_NAME=hello-world

all: check build

build:
	@go build -o ${BINARY_NAME} hello.go
# 	GOARCH=amd64 GOOS=darwin go build -o ${BINARY_NAME}-darwin hello.go
# 	GOARCH=amd64 GOOS=linux go build -o ${BINARY_NAME}-linux hello.go
# 	GOARCH=amd64 GOOS=window go build -o ${BINARY_NAME}-windows hello.go

clean:
	@go clean
	rm ${BINARY_NAME}
# 	rm ${BINARY_NAME}-darwin
# 	rm ${BINARY_NAME}-linux
# 	rm ${BINARY_NAME}-windows

test:
	@go test ./...

test_coverage:
	@go test ./... -coverprofile=coverage.out

check:
	@go fmt ./
	@go vet ./

run:
	./${BINARY_NAME}

dep:
	@go mod download

lint:
	@golangci-lint run --enable-all
