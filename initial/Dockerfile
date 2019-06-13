FROM certbot/certbot
VOLUME /var/www/certbot
ENTRYPOINT ["/bin/sh","-c" ]
CMD ["certbot certonly \
                --webroot -w /var/www/certbot \
                --email $EMAIL \
                --no-eff-email \
                --agree-tos \
                --rsa-key-size 4096 \
                 -d $DOMAIN"]
