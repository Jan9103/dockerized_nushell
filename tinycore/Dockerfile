# download ca-certificates (required for ssl)
FROM alpine as certs
RUN apk update && apk add ca-certificates

FROM tdshi/tinycore:latest
COPY --from=certs /etc/ssl/certs /etc/ssl/certs

COPY nu /bin/nu

ENTRYPOINT ["nu"]
