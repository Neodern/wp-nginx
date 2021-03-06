WP-Nginx
============

WP-Nginx is a model of [Nginx](http://nginx.org) configuration for your [WordPress](http://wordpress.org) website using SSL [Letsencrypt](https://letsencrypt.org/).

## <a name='toc'>Table of Contents</a>

  1. [Contributors](#contributors)
  1. [Before You Start](#before)
  1. [Configuration](#configuration)
  1. [License](#license)

## <a name='contributors'>Contributors</a>

The configuration was created and is maintained by [Nicolas Jamet](http://www.neodern.fr) ([@neodern](http://twitter.com/neodern)).

## <a name='before'>Before You Start</a>
This configuration file has been tested on Debian 7 and SSL certificates generated by [Certbot](https://github.com/certbot/certbot). 
Feel free to fork this project and send a PR with your optimisations or contact me. ;)  



## <a name='configuration'>Configuration</a>

  1. Step 1 : replace all `exemple.com` with your domain name.
  1. Step 2 : Edit values below
          
 ```
  set $wpn_yoast_seo_plugin 1;    # set to 0 if you don't use YOAST SEO Plugin, but you should use it. ;)

  # Basic configuration
  server_name www.exemple.com;
  root /var/www/site-directory/;
  index index.php;

  # Logs
  access_log /var/log/exemple.access.log;
  error_log /var/log/exemple.error.log;

  # SSL public and private keys
  ssl_certificate /etc/letsencrypt/live/www.exemple.com/fullchain.pem;
  ssl_certificate_key /etc/letsencrypt/live/www.exemple.com/privkey.pem;

  ##
  # Rocket-Nginx configuration
  ##
  # Uncomment it if you use wp-rocket Plugin and rocket-nginx configuration
  # wp-rocket : https://wp-rocket.me/
  # rocket-nginx : https://github.com/maximejobin/rocket-nginx
  ##
  #include rocket-nginx/rocket-nginx.conf;
  
  ```

## <a name='license'>License</a>
Released under the [MIT](https://github.com/Neodern/wp-nginx/blob/master/LICENSE). See the link for details.