# immagine ufficiale python leggera
FROM python:3.13-slim

# download git & clone repo
RUN apt-get update && apt-get install -y git && rm -rf /var/lib/apt/lists/*

RUN git clone https://github.com/mmenapace/SomeBankingApp /app_repo

# Impostiamo la working directory nella cartella del backend all'interno del repo clonato
WORKDIR /app_repo/backend

# Installiamo le dipendenze Python specificate 
RUN pip install --no-cache-dir -r requirements.txt fastapi uvicorn
# Esponiamo la porta su cui gira il backend (es. 8000)
EXPOSE 8000

# Comando di avvio dell'applicazione
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000", "--root-path", "/api"]