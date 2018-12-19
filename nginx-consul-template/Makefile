all: push

build:
	docker build -t localhost:6000/nginx-consul-template .

push: build
	docker push localhost:6000/nginx-consul-template:latest

