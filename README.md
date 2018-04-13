# letsencrypt-cronautorenew

A bash script to auto-renew Let's Encrypt SSL certificates on an Apache web server.

## Installation

### Get files
Copy the content of this repo into your users **Let's Encrypt** home directory.

### Create a symlink
Inside the cronautorenew-dir, create a symlink to your letsencrypt-auto script. The link has to be called `letsencrypt-auto`
```
ln -s ../letsencrypt/letsencrypt-auto ./letsencrypt-auto
```

### Edit domain.conf

Write one domain per line. Alternatively, you can write domains on separate lines for multi-domain certificates.

```
# Domains on one line
example.com www.example.com
# Alternatively, you can write one domain per line
flamethrower.com
sherlock.com
```

### Create a CRON job

execute `crontab -e` logged in as your letsencrypt-user and creates a CRON job.

# CRON job example

@daily /PathToLetsencrypt/letsencrypt/cronautorenew.sh

## Log File
It will redirect all input to a log file on execution. You'll find it in your auto-renew directory, and it is called "cert_renew.log"