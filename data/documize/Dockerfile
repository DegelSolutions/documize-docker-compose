FROM alpine as build-env

ENV DOCUMIZEVERSION=v5.2.1

RUN apk update \
    && apk add curl \
    && curl -L https://github.com/documize/community/releases/download/${DOCUMIZEVERSION}/documize-community-linux-amd64 --output /usr/local/bin/documize \
    && chmod +x /usr/local/bin/documize

FROM scratch
COPY --from=build-env /usr/local/bin/documize /
ENTRYPOINT ["/documize"]
