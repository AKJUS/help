# Let's Encrypt

## Reloading Webserver after Renewal

If you're using Let's Encrypt, then don't forget that your webserver needs to be reloaded once the certificate has been renewed, otherwise your visitors will end up with an error message from their browser. 

For that, you can create the file `/etc/letsencrypt/renewal-hooks/post/reload-webserver.sh` with following content:

```
#!/bin/sh

printf '%s\n' "Attempt to reload webserver after Let's Encrypt TLS certificate renewal:"

# Apache
if systemctl is-active apache2 >/dev/null
then
	if systemctl reload apache2
	then
		printf '%s\n' "  apache2 successfully reloaded."
	fi
# nginx
elif systemctl is-active nginx >/dev/null
then
	if systemctl reload nginx
	then
		printf '%s\n' "  nginx successfully reloaded."
	fi
else
	printf '%s\n' "  No running webserver found."
fi
```

Make it executable:

```
chmod +x /etc/letsencrypt/renewal-hooks/post/reload-webserver.sh
```
