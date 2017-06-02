# A makefile to build the docker images for caffe.

DOCKER ?= docker

all: jupyter

.PHONY: gosu jupyter

gosu: gosu/Dockerfile
	$(DOCKER) build -t caffe-pruning:gosu gosu/

jupyter: jupyter/Dockerfile
	$(DOCKER) build -t caffe-pruning:gosu gosu/
	$(DOCKER) build -t caffe-pruning:jupyter jupyter/
