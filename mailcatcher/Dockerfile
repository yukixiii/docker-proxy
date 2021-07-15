FROM ruby:3.0-alpine

RUN apk --no-cache --update add \
                            libstdc++ \
                            build-base \
                            openssl-dev \
                            sqlite \
                            sqlite-dev \
                            ruby-dev && \
    gem install mailcatcher && \
    apk del build-base ruby-dev && \
    rm -rf /tmp/* /var/tmp/* /var/cache/apk/*

# smtp (25) and ip (80) ports
# EXPOSE 1025 1080
EXPOSE 25 80

CMD ["mailcatcher", "--smtp-ip=0.0.0.0", "--smtp-port=25", "--http-ip=0.0.0.0", "--http-port=80", "-f"]
