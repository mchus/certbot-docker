FROM certbot/certbot
VOLUME /var/www/certbot
ENTRYPOINT ["/bin/sh","-c" ]
CMD ["certbot renew && sleep 1d"]
