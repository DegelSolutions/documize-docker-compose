FROM alpine as build

ARG DOCUMIZE_BINARY_URL

RUN apk update \
    && apk add curl \
    && curl -L ${DOCUMIZE_BINARY_URL} --output /usr/local/bin/documize \
    && chmod +x /usr/local/bin/documize

FROM gcr.io/distroless/static AS final
USER nonroot:nonroot
COPY --from=build /usr/local/bin/documize /
ENTRYPOINT ["/documize"]
