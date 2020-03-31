# certbot-docker
Fire and forget Let's Encrypt certification generator  containers.

## Usage
### 1. Preflight check
Set environment options:
  - `EMAIL`
  - `DOMAIN`

Create or map volume for ssl certificate:
  - `/etc/letsencrypt`

### 2. Generate certificate
Run `mchus/certbot:initial`
Certbot will automatically register your domain name and then container stops. Check container logs for  information.

```docker run --name certbot_initial \
-v /etc/letsencrypt:/etc/letsencrypt \
-v /var/www/certbot:/var/www/certbot \
-e EMAIL=steve@apple.com \
-e DOMAIN=apple.com \
-p 80:80 \
--rm mchus/certbot:initial```


### 3. Start renewal container
Run `mchus/certbot:renewal`
Container will renew you certificate every day and then exits. You need to automatically restart container to maintain certificate availability for your domain.

```docker run --name certbot_renewal \
-d mchus/certbot:initial```
