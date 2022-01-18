.PHONY: all build clean run check cover lint docker help

BINARY_NAME=math

all: check build

build:
	@go build -o ${BINARY_NAME} math.go

clean:
	@go clean
	rm ${BINARY_NAME}

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
