# Utilizziamo un'immagine ufficiale Python leggera
FROM python:3.13-slim

# Installiamo git per poter clonare il repository
RUN apt-get update && apt-get install -y git && rm -rf /var/lib/apt/lists/*

# Cloniamo il repository direttamente durante la build
# (Sostituisci l'URL con il link corretto del tuo repository GitHub)
RUN git clone https://github.com/mmenapace/SomeBankingApp /app_repo

# Impostiamo la working directory nella cartella del backend all'interno del repo clonato
WORKDIR /app_repo/backend

# Installiamo le dipendenze Python specificate in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt fastapi uvicorn
# Esponiamo la porta su cui gira il backend (es. 8000)
EXPOSE 8000

# Comando di avvio dell'applicazione
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000", "--root-path", "/api"]