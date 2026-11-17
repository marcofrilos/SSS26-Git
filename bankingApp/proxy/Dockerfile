FROM nginx:alpine

# Rimozione configurazione prredefininita di nginx e sostituzione con la nostra configurazione personalizzata del reverse proxy
RUN rm /etc/nginx/conf.d/default.conf

COPY nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80