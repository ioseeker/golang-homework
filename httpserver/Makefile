export tag=v1.0
root:
	export ROOT=github.com/ioseeker/golang-homework

build:
	echo "building httpserver binary"
	mkdir -p bin/amd64
	CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -o bin/amd64 .

release: build
	echo "building httpserver container"
	docker build -t ioseeker/httpserver:${tag} .

push: release
	echo "pushing ioseeker/httpserver"
	docker push ioseeker/httpserver:v1.0
