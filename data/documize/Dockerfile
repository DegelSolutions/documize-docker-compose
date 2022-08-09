FROM ubuntu:20.04 as build-env

ENV DOCUMIZEVERSION=v5.2.1

RUN apt-get update -y \
    && apt-get install -y wget \
    && wget -O /usr/local/bin/documize https://github.com/documize/community/releases/download/${DOCUMIZEVERSION}/documize-community-linux-amd64 \
    && chmod +x /usr/local/bin/documize

FROM gcr.io/distroless/base-debian10
COPY --from=build-env /usr/local/bin/documize /
ENTRYPOINT ["/documize"]
