# Nushell Docker

A dockerized nushell instance.

Why?
- it provides a minimal config, which helps with bug-reporting
- i was bored

## Variants

### slim
Based on: `debian:slim`

Additions:
- ca-certificates (required for https, etc)
- curl, tar, jq (required for installation)
- `nu-latest-x84_64-unknown-linux-gnu` from github

Build it: `docker build -t nushell:slim slim`

Run it: `docker run --rm -it nushell:slim`
