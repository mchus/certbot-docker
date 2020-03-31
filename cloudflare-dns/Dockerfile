FROM certbot/certbot
VOLUME /var/www/certbot
ENTRYPOINT ["/bin/sh","-c" ]
CMD ["certbot certonly \
                --dns-cloudflare \
							  --dns-cloudflare-credentials \
                --dns-cloudflare-propagation-seconds 60 \
								--email $EMAIL \
                --no-eff-email \
                --agree-tos \
                --rsa-key-size 4096 \
                 -d $DOMAIN"]
