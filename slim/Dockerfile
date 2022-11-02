FROM debian:stable-slim

RUN apt-get update && \
	apt-get install -y --no-install-recommends curl tar jq ca-certificates && \
	update-ca-certificates && \
	rm -rf /usr/share/doc /usr/share/man /usr/share/locale /usr/share/info /var/cache/apt /var/lib/apt/lists /var/log /var/lib/dpkg/*-old

#RUN curl -L "https://github.com/nushell/nushell/releases/download/0.70.0/nu-0.70.0-x86_64-unknown-linux-gnu.tar.gz" -o nu.tar.gz && \
RUN curl -L -o nu.tar.gz "$(curl -L "https://api.github.com/repos/nushell/nushell/releases" | jq -r '.[0].assets | .[] | select(.name|test("x86_64-unknown-linux-gnu.tar.gz$")) | .browser_download_url')" && \
	tar -xf nu.tar.gz nu && \
	rm nu.tar.gz && \
	mv nu /bin

ENTRYPOINT ["nu"]
