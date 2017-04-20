# Tessel Websites 

We use the following major services:

1. AWS for Route 53 (DNS) and S3
2. Dokku on DigitalOcean for most services
3. Bocoup infrastructure for tessel.io and Forums

## Dokku

We have a large Dokku instance for setting up new pages. It can run containers and Heroku buildpacks, which is rad. You'll need two things:

1. Access to dokku.tessel.io via SSH
2. Access to AWS via our login credentials

### Setting up a new app

Login to the server `ssh root@dokku.tessel.io`.

To create a new app:

```
dokku apps:create NEWAPP
```

On your local computer, add it as a remote to your git repo:

```
git remote add dokku dokku@dokku.tessel.io:NEWAPP
git push dokku master
```

You'll see the following:

```
...
=====> Application deployed:
       http://107.170.4.104:<port number>

To dokku@107.170.4.104:NEW_APP
   xxxxxx..xxxxxx  master -> master
Branch master set up to track remote branch master from dokku.
```

If you want to view your app *now*, you'll have to expose the port directly on the server:

```
ufw allow <port number>
```

Then you can open `http://107.170.4.104:<port number>` in your browser.

### Adding a .tessel.io subdomain

Use Route 53 to modify this. Create a new A record under the "tessel.io" hosted zone, make the subdomain named what you want. Set its value to "107.170.4.104", and TTL to 5m or 1m.

**NOTE:** It's preferred that subdomains and the name of the Dokku app match exactly.

You can now enable the subdomain using this command on the Dokku server:

```
dokku domains:add NEWAPP NEWAPP.tessel.io
```

You can enable HTTPS very simply with the following:

```
dokku config:set --no-restart NEWAPP DOKKU_LETSENCRYPT_EMAIL=team@tessel.io
dokku letsencrypt NEWAPP
```

Now all HTTP requests will automatically redirect. And you're done!

### Troubleshooting

Look up logs with Dokku while logged into the server:

```
dokku logs NEWAPP
```
