# certbot-docker
Fire and forget Let's Encrypt certification generator  containers.

## Usage
### 1. Preflight check
Set environment options:
  - `EMAIL`
  - `DOMAIN`

Create or map volume for ssl certificate:
  - `/var/www/certbot`

### 2. Generate certificate
Run `mchus/certgot:initial`
Certbot will automatically register your domain name and then container stops. Check container logs for  information.

### 3. Start renewal container
Run `mchus/certbot:renewal`
Container will renew you certificate every day and then exits. You need to automatically restart container to maintain certificate availability for your domain.
