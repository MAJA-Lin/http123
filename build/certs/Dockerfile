FROM alpine:latest

RUN apk upgrade --update-cache --available && \
    apk add openssl && \
    rm -rf /var/cache/apk/*

COPY ./ssl.conf /var/certs/ssl.conf

RUN openssl req -x509 -new -nodes -sha256 -utf8 -days 3650 \
    -newkey rsa:4096 -keyout /var/certs/localhost.key \
    -out /var/certs/localhost.crt -config /var/certs/ssl.conf


RUN openssl req -x509 -newkey rsa:4096 -days 3650\
    -sha256 -nodes \
    -keyout /var/certs/rsa-pss.key \
    -out /var/certs/rsa-pss.crt -config /var/certs/ssl.conf

# RUN openssl pkcs12 -export -in /var/certs/localhost.crt \
#     -inkey /var/certs/localhost.key \
#     -out /var/certs/localhost.pfx

COPY ./dhparam.pem /var/certs/dhparam.pem

ENTRYPOINT [ "tail", "-f", "/dev/null" ]
