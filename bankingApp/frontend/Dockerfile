# --- STADIO 1: Build dell'applicazione Angular ---
FROM node:20-alpine AS builder

# Installiamo git
RUN apk add --no-cache git

# Cloniamo il repository
RUN git clone https://github.com/mmenapace/SomeBankingApp /app_repo

WORKDIR /app_repo/frontend

# Installazione delle dipendenze e compilazione di produzione
RUN npm install
RUN npm run build -- --configuration production

# --- STADIO 2: Server Nginx per servire i file statici ---
FROM nginx:alpine

# Copia i file compilati di Angular dalla fase precedente alla cartella di default di Nginx
# (Verifica il percorso esatto della build in base alla versione di Angular, es. dist/ o dist/browser)
COPY --from=builder /app_repo/frontend/dist/SomeBankingFrontend/browser/ /usr/share/nginx/html/
# Esponiamo la porta 80 del web server
EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]