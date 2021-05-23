ARG BUILD_FROM
FROM alpine:3.13

# Add env
ENV LANG C.UTF-8

# Set shell
SHELL ["/bin/sh", "-o", "pipefail", "-c"]
EXPOSE 3000/tcp

RUN apk add --no-cache \
    bash \
    nodejs \
    npm \
    ffmpeg \
    git && \
    cd / && \
    git clone https://github.com/servervas/ring-hassio && \
    cd ring-hassio/ring_hassio && \
    npm install --unsafe-perm && \
    chmod a+x run.sh

CMD [ "/ring-hassio/ring_hassio/run.sh" ]
