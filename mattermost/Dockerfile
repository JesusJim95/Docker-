FROM nginx:latest

COPY ./conf_mattermost.conf /etc/nginx/conf.d/
COPY ./fullchain.pem /etc/letsencrypt/live/mattermost.jjimenez.nosolosoftware.es/
COPY ./privkey.pem /etc/letsencrypt/live/mattermost.jjimenez.nosolosoftware.es/

CMD ["nginx", "-g", "daemon off;"]

