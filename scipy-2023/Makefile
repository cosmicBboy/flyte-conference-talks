VERSION=$(shell git rev-parse HEAD | cut -c1-7)

docker-build:
	docker buildx build --push . --platform=linux/amd64,linux/arm64 \
		-t ghcr.io/flyteorg/flyte-conference-talks:scipy-2023-${VERSION} \
		-t ghcr.io/flyteorg/flyte-conference-talks:scipy-2023-latest

ci-docker-build:
	docker build --push . -f Dockerfile.ci -t ghcr.io/flyteorg/flyte-conference-talks:scipy-2023-ci

sandbox-docker-build:
	docker build --push . -t localhost:30000/flyte-conference-talks:scipy-2023-ci --platform=linux/amd64,linux/arm64

wget-docker-build:
	docker build --push . -f Dockerfile.wget --platform=linux/amd64,linux/arm64 \
		-t ghcr.io/flyteorg/flyte-conference-talks:scipy-2023-wget-${VERSION} \
		-t ghcr.io/flyteorg/flyte-conference-talks:scipy-2023-wget-latest
