# Sample Piku app

This is an example rails app, with a Procfile to use sqlite3 on [piku](https://github.com/piku/piku).

Tweaks you'll need:
- Create your own master.key file
- Edit your protected credentials with `rails credentials:edit` and set a value for `secret_key_base`

These changes are needed since it's insecure to publish my master.key.

After you deploy this app to your piku server, add an ENV var for your master key and host name:
```bash
piku config:set RAILS_MASTER_KEY=$(cat config/master.key)
piku config:set NGINX_SERVER_NAME=rails.example.com
```

## TOOD

### Remove hard-coded port
I've hardcoded the port with the ENV var `PORT`, instead of letting the uwsgi daemon pick it. I don't recall the reason now and need to debug the problem.