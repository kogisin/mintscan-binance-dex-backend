# VERSION               := $(shell echo $(shell git describe --tags) | sed 's/^v//')
VERSION 			  ?= manual
COMMIT                := $(shell git log -1 --format='%H')
TOOLS_DESTDIR         ?= $(GOPATH)/bin/chain-exporter
BUILD_FLAGS 		  := -ldflags "-X main.buildHash=${COMMIT} -X util.BuildVersion=${VERSION}"

build: go.sum
	@echo "building chain-exporter binary..."
	@go build -mod=readonly $(BUILD_FLAGS) -o $(TOOLS_DESTDIR) .
	#GOARCH=amd64 CGO_ENABLED=0 GOOS=linux go build $(BUILD_FLAGS) -o $(TOOLS_DESTDIR) .

install: go.sum
	@echo "installing chain-exporter binary..."
	@go install -mod=readonly $(BUILD_FLAGS) .

clean:
	@echo "cleaning chain-exporter binary..."
	rm -f $(TOOLS_DESTDIR) 2> /dev/null
