### GET ###
FROM alpine:latest as get

# prepare environment
WORKDIR /tmp
RUN apk --no-cache add unzip

# get bun
ADD https://github.com/oven-sh/bun/releases/latest/download/bun-linux-aarch64.zip bun-linux-aarch64.zip
RUN unzip bun-linux-aarch64.zip

### IMAGE ###
FROM debian:bookworm-slim

# install bun
COPY --from=get /tmp/bun-linux-aarch64/bun /usr/local/bin

# smoke test
RUN bun --version
