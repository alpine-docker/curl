#FROM alpine:latest
FROM alpine:3.14
RUN apk add --update curl && rm -rf /var/cache/apk/*
COPY entrypoint.sh /
ENTRYPOINT ["/entrypoint.sh"]
CMD ["curl"]
