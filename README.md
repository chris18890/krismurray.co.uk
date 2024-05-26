# krismurray.co.uk
==============

# install

## git instructions

```
sudo rm -rf mts-site /var/www/krismurray-ssl
```

### git url

```
eval $(ssh-agent -s); ssh-add .ssh/github_rsa
git clone git@github.com:chris18890/krismurray.co.uk.git
sudo cp -r krismurray.co.uk/krismurray/ /var/www/krismurray-ssl; sudo chown www-data -R /var/www
```

# Setup - multiple domains/ssl sites

```
nano krismurray.co.uk/krismurray-ssl.conf
sudo cp krismurray.co.uk/krismurray-ssl.conf /etc/apache2/sites-available/krismurray-ssl.conf; sudo a2ensite krismurray-ssl; sudo service apache2 restart
sudo certbot --apache -d krismurray.co.uk -d www.krismurray.co.uk --agree-tos --renew-by-default --no-redirect
```
