# build app angular
FROM node:20-alpine AS builder

# installazine git per clonare la repo
RUN apk add --no-cache git

RUN git clone https://github.com/mmenapace/SomeBankingApp /app_repo

WORKDIR /app_repo/frontend

# installazione delle dipendenze e compilazione di produzione
RUN npm install
RUN npm run build -- --configuration production

# server Nginx per file statici
FROM nginx:alpine

# Copia file compilati di Angular dalla fase precedente alla cartella di default di Nginx
COPY --from=builder /app_repo/frontend/dist/SomeBankingFrontend/browser/ /usr/share/nginx/html/
# Esponiamo la porta 80 del web server
EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]