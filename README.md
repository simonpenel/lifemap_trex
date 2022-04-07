# INSTALLATION DU SERVER LIFEMAP/TREX

1. Installer et lancer lifemap

2. Installer et lancer trex

## Pour finir, configurer ngnix:

modifier les 2 fichiers:

- /etc/nginx/sites-available/default
- /etc/nginx/sites-enabled/trex

Contenu des 2 fichiers:
   
    server {
     listen 80;
     server_name trex.univ-lyon1.fr;
     client_max_body_size 10m ;
     location / {
     include proxy_params;
     proxy_pass http://127.0.0.1:6767;
     }
    }

Et relancer:

`sudo service apache2 restart`
