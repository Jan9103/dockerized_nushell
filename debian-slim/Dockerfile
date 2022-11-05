FROM debian:stable-slim

# install ca-certificates (required for https) and clean up after apt
RUN apt-get update && \
	apt-get install -y --no-install-recommends ca-certificates && \
	update-ca-certificates && \
	rm -rf /usr/share/doc /usr/share/man /usr/share/locale /usr/share/info /var/cache/apt /var/lib/apt/lists /var/log /var/lib/dpkg/*-old

COPY nu /usr/local/bin/nu

ENTRYPOINT ["nu"]
