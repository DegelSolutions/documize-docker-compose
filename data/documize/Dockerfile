FROM alpine as build

ENV DOCUMIZEVERSION=v5.2.1

RUN apk update \
    && apk add curl \
    && curl -L https://github.com/documize/community/releases/download/${DOCUMIZEVERSION}/documize-community-linux-amd64 --output /usr/local/bin/documize \
    && chmod +x /usr/local/bin/documize

FROM gcr.io/distroless/static AS final
USER nonroot:nonroot
COPY --from=build /usr/local/bin/documize /
ENTRYPOINT ["/documize"]
