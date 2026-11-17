FROM nginx:alpine

# Rimuoviamo la configurazione predefinita di Nginx
RUN rm /etc/nginx/conf.d/default.conf

# Copiamo la nostra configurazione personalizzata del reverse proxy
COPY nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80