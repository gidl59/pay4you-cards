
# Pay4You Cards — "Tipo AI Card"
Mini‑piattaforma per biglietti digitali con QR + vCard + NFC.

## Funzioni
- Gestione agenti (CRUD) con login
- Pagina pubblica per ogni agente: `https://TUO-DOMINIO/<slug>`
- vCard diretta: `https://TUO-DOMINIO/<slug>.vcf`
- QR code automatico: `https://TUO-DOMINIO/<slug>/qr.png`
- Stile blu+oro coerente con Pay4You
- Pronta per collegare NFC (scrivi l'URL della card sul tag)

## Setup locale (5 minuti)
```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
cp .env.example .env
# apri .env e imposta ADMIN_PASSWORD, BASE_URL e APP_SECRET
python app.py
# apri http://localhost:8000
```

## Deploy su hosting (es. Aruba / VPS)
- Carica i file della cartella
- Se supporta Python WSGI, usa `gunicorn "app:app"`
- In alternativa, deploy su Docker/Render/Heroku
- Imposta variabili ambiente: `ADMIN_PASSWORD`, `BASE_URL=https://pay4you.store`, `APP_SECRET`

## Creazione primo agente
1. Vai su `/login` e inserisci la password admin (da `.env`)
2. "Nuovo agente" e compila i campi
3. La card sarà visibile su `https://pay4you.store/<slug>`

## NFC
Scrivi sul tag l'URL `https://pay4you.store/<slug>` con l'app **NFC Tools**.
