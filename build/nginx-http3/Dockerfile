# Config certs
FROM certs-carrier:stable AS certs

# Base Nginx HTTP/3 Image
FROM ranadeeppolavarapu/nginx-http3:latest

# Copy certs.
COPY --from=certs /var/certs/dhparam.pem /etc/nginx/dhparam.pem
COPY --from=certs /var/certs/localhost.key /etc/ssl/localhost.key
COPY --from=certs /var/certs/localhost.pem /etc/ssl/localhost.pem

COPY conf/nginx.conf /etc/nginx/nginx.conf
COPY conf/example.com.conf /etc/nginx/conf.d/default.conf
