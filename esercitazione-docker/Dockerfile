FROM nginx:alpine

LABEL maintainer="studente@unige.it"
ENV APP_ENV=development

WORKDIR /usr/share/nginx/html

COPY html/ ./

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
