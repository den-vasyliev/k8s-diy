DOCKER_IMAGE_VERSION=1.1.20
DOCKER_IMAGE_NAME=denvasyliev/rpi-nano-httpd
DOCKER_IMAGE_TAGNAME=$(DOCKER_IMAGE_NAME):$(DOCKER_IMAGE_VERSION)

default: build

build:
	docker build -t $(DOCKER_IMAGE_TAGNAME) --no-cache .
	docker tag $(DOCKER_IMAGE_TAGNAME) $(DOCKER_IMAGE_NAME):latest

minimal:
	docker build -t $(DOCKER_IMAGE_TAGNAME) -f Dockerfile.minimal .
	docker tag  $(DOCKER_IMAGE_TAGNAME) $(DOCKER_IMAGE_NAME):minimal

push:
	docker push $(DOCKER_IMAGE_NAME)

run:
	docker run -d -p 80:80 -d hypriot/rpi-nano-httpd
