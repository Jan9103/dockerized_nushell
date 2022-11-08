IMAGE_NAME = "nushell:busybox"


.PHONY: download_nu
download_nu:
	curl -L -o nu.tar.gz "$$(curl -L "https://api.github.com/repos/nushell/nushell/releases" | jq -r '.[0].assets | .[] | select(.name|test("x86_64-unknown-linux-musl.tar.gz$$")) | .browser_download_url')"
	tar -xf nu.tar.gz "$$(tar -tf nu.tar.gz | grep 'nu$$')"
	rm nu.tar.gz && mv */nu . && rmdir */

.PHONY: build_docker_image
build_docker_image:
	docker build -t $(IMAGE_NAME) .

.PHONY: build
build: download_nu build_docker_image

.PHONY: run
run:
	docker run --rm -it $(IMAGE_NAME)
