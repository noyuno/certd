# certd

deploy Let's Encrypt certificates with SSH

## usage

### server

~~~
<create certificates>
./deployinit
ssh-keygen -t rsa -f id_rsa -N ''
<copy id_rsa.pub to childs' ~/.ssh/authorized_keys>
<edit domain, child, user in config>
<deploy certd repo to child servers>
~~~

certificates' renew through cron

renew certificates' manually:

~~~
sudo certbot renew --webroot -w /var/www/cert --renew-hook deploy --allow-subset-of-names
~~~

### child servers

~~~
./watchinit
~~~

check whether running certwatch service:

~~~
sudo systemd status certwatch
~~~

