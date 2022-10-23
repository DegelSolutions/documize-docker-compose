FROM alpine as build

ENV DOCUMIZEVERSION=v5.4.1

RUN apk update \
    && apk add curl \
    && curl -L https://community-downloads.s3.us-east-2.amazonaws.com/documize-community-plus-linux-amd64 --output /usr/local/bin/documize \
    && chmod +x /usr/local/bin/documize

FROM gcr.io/distroless/static AS final
USER nonroot:nonroot
COPY --from=build /usr/local/bin/documize /
ENTRYPOINT ["/documize"]
