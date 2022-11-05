# Nushell Docker

A dockerized nushell instance.

## Features
- enters nu on start
- ca-certificates are installed (required for ssl)

## Usage
Dependencies:
- [docker](https://docs.docker.com/)
### Building using the Makefiles
Dependencies:
- [curl](https://github.com/curl/curl)
- [GNU make](https://www.gnu.org/software/make/)
- [GNU tar](https://git.savannah.gnu.org/git/tar.git/)
- [jq](https://stedolan.github.io/jq/)

1. go to the directory of the version you would like to build
2. run `make build`

### Building it manually
1. go to the directory of the version you would like to build
2. copy a version of the `nu` binary to the directory
3. run `docker build -t nushell:VARIANT .`

### Running it
`docker run --rm -it nushell:VARIANT`.  
Example: `docker run --rm -it nushell:debian-slim`.

## Variants

`debian-slim` is recommended for the average user.

Name            | base-image              | nu-version         | image size
--------------- | ----------------------- | ------------------ | ----------
`alpine`        | `alpine:latest`         | latest, linux-musl | 76.3MB
`busybox`       | `busybox:stable`        | latest, linux-musl | 72.3MB
`debian-slim`   | `debian:slim`           | latest, linux-gnu  | 154MB
`gentoo-stage3` | `gentoo/stage3:latest`  | latest, linux-gnu  | 268MB
`tinycore`      | `tdshi/tinycore:latest` | latest, linux-musl | 80.9MB
