# cert

deploy Let's Encrypt certificates with SSH

## usage

### server

~~~
<create certificates>
./deployinit
ssh-keygen -t rsa -f id_rsa -N ''
<copy id_rsa.pub to clients' ~/.ssh/authorized_keys>
~~~

certificates' renew through cron

renew certificates' manually:

~~~
sudo certbot renew --webroot -w /var/www/cert --renew-hook /home/noyuno/cert/deploy --allow-subset-of-names
~~~

### client

~~~
./watchinit
~~~

check whether running certwatch service:

~~~
sudo systemd status certwatch
~~~

