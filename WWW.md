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

To create a new app, run this command on the server:

```
server> dokku apps:create NEWAPP
```

On your local computer, add it as a remote to your git repo:

```
local> git remote add dokku dokku@dokku.tessel.io:NEWAPP
local> git push dokku master
```

You'll see the following:

```
server> ...
server> =====> Application deployed:
server>        http://dokku.tessel.io:<port number>
server> 
server> To dokku@dokku.tessel.io:NEW_APP
server>    xxxxxx..xxxxxx  master -> master
server> Branch master set up to track remote branch master from dokku.
```

If you want to view your app *now*, you'll have to expose the port directly on the server:

```
server> ufw allow <port number>
```

Then you can open `http://dokku.tessel.io:<port number>` in your local web browser.

### Adding a .tessel.io subdomain

Use Route 53 to modify this. Create a new record under the "tessel.io" hosted zone with these properties:

* Subdomain field should be "NEWAPP"
* CNAME record
* Value set to "dokku.tessel.io"
* TTL to 5m or 1m.

**NOTE:** It's preferred that subdomains and the name of the Dokku app match exactly.

You can now enable the subdomain using this command on the Dokku server:

```
server> dokku domains:add NEWAPP NEWAPP.tessel.io
```

You can enable HTTPS very simply with the following:

```
server> dokku config:set --no-restart NEWAPP DOKKU_LETSENCRYPT_EMAIL=team@tessel.io
server> dokku letsencrypt NEWAPP
```

Now all HTTP requests will automatically redirect. And you're done!

### Troubleshooting

Look up logs with Dokku while logged into the server:

```
server> dokku logs NEWAPP
```
