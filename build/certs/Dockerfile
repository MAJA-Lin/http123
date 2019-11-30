FROM alpine:latest

COPY ./dhparam.pem /var/certs/dhparam.pem
COPY ./localhost.key /var/certs/localhost.key
COPY ./localhost.pem /var/certs/localhost.pem

ENTRYPOINT [ "tail", "-f", "/dev/null" ]
