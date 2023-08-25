# Web Server

> This is a quickStart to set up web server with nginx on local machine.

## Installation

1. install nginx
```sh
sudo apt install nginx
```

2. start nginx
```sh
sudo systemctl start nginx
```

3. enable nginx start on boot
```sh
sudo systemctl enable nginx
```

## Map port to service

1. open the config file
```sh
sudo nano /etc/nginx/sites-available/default
```

2. add the server you would like to map
```conf
server {
	listen 5173 default_server;
	listen [::]:5173 default_server;

		root <path-to-your-static-files>

	index index.html

	server_name _;

	}

}
```
:exclamation: Access to root folder may be denied.
> change the user of nginx to the owner of the static files at `/etc/nginx/nginx.conf`

## Restart service

1. Test the configuration

```sh
sudo nginx -t
```

2. Restart Nginx

```sh
sudo systemctl restart nginx
```
