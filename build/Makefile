# Etherpad-lite Docker Image

.PHONY: help
help:
        @echo ""
        @echo "Usage: make COMMAND"
        @echo ""
        @echo "Docker etherpad image makefile"
        @echo ""
        @echo "Commands:"
        @echo "  build        Build and tag image"
        @echo "  push         Push tagged image to registry"
        @echo "  delete       Delete all built image versions"
        @echo ""

IMAGE=etherpad
TAG=latest
REGISTRY=4ss078

.PHONY: build
build:
        @docker build -t ${REGISTRY}/${IMAGE}:${TAG} .

.PHONY: push
push:
        @docker push ${REGISTRY}/${IMAGE}:${TAG}

.PHONY: delete
delete:
        @docker image ls | grep ${IMAGE} | awk '{print $$3}' | xargs -I + docker rmi +
