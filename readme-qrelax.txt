# 🏠 QRelax - Sistema Completo

Sistema di guide digitali per appartamenti in affitto breve con Dashboard Host integrata.

---

## 📁 STRUTTURA FILE

```
qrelax/
├── index.html           # Webapp principale (motore)
├── dashboard.html       # Dashboard per host
├── feedback.html        # Form feedback ospiti
├── papaya.json          # Esempio dati Appartamento Papaya
├── template.json        # Template per nuovi clienti
└── README.md           # Questa guida
```

---

## 🚀 SETUP INIZIALE

### 1. Carica su GitHub
- Crea un nuovo repository su GitHub
- Carica tutti i file
- Vai su **Settings → Pages**
- Seleziona branch **main** e salva

### 2. URL Finale
Il tuo sito sarà disponibile su:
```
https://tuonome.github.io/qrelax
```

---

## 📱 WEBAPP OSPITI (index.html)

### Funzionalità:
- ✅ Multilingua (IT/EN/DE)
- ✅ Dark mode automatico
- ✅ Meteo in tempo reale
- ✅ Filtri ristoranti (prezzo, distanza)
- ✅ Info WiFi con copia password
- ✅ Mappe integrate
- ✅ Galleria foto
- ✅ Accessibilità ottimizzata
- ✅ Tracking visite automatico

### Come testare:
```
https://tuosito.github.io/qrelax?apt=papaya
```

Per tracking QR code:
```
https://tuosito.github.io/qrelax?apt=papaya&source=qr
```

---

## 🎯 DASHBOARD HOST (dashboard.html)

### Accesso Demo:
- **Email:** leonardo@qrelaxing.com
- **Password:** demo123

### Funzionalità:
- 📊 Statistiche visualizzazioni
- 📱 Contatore QR code scansionati
- ⭐ Valutazione media
- 💬 Feedback ospiti in tempo reale
- 📈 Grafico visite ultimi 30 giorni
- 🎯 QR code generato
- 🕒 Log visite recenti

### Statistiche Tracciate:
- Numero totale visualizzazioni
- Sorgente traffico (QR vs Link)
- Data e ora accessi
- Valutazioni medie
- Feedback testuale

---

## ⭐ FEEDBACK OSPITI (feedback.html)

Form per raccogliere recensioni da:
```
https://tuosito.github.io/qrelax/feedback.html?apt=papaya
```

### Campi:
- Valutazione 1-5 stelle (obbligatorio)
- Nome (opzionale)
- Email (opzionale)
- Commento (obbligatorio, max 500 caratteri)

I feedback vengono:
1. Salvati in localStorage (demo)
2. Mostrati nella Dashboard Host
3. Usati per calcolare valutazione media

---

## 📝 CREARE NUOVO CLIENTE

### Passo 1: Copia Template
```bash
cp template.json nuovo-cliente.json
```

### Passo 2: Modifica Dati
Apri `nuovo-cliente.json` e sostituisci:

```json
{
  "nome": "Villa Sunset",
  "indirizzo": "Via Mare 15, Rimini",
  "lat": 44.0678,
  "lon": 12.5695,
  "wifi_ssid": "VillaSunset_WiFi",
  "wifi_password": "sunset2025",
  "host_telefono": "+39 333 123456",
  "host_email": "host@email.it",
  ...
}
```

### Passo 3: Carica su GitHub
- Upload file `nuovo-cliente.json`
- Commit e push

### Passo 4: Genera QR Code
URL da usare nel QR:
```
https://tuosito.github.io/qrelax?apt=nuovo-cliente&source=qr
```

**Generatori QR consigliati:**
- [QR Code Generator](https://www.qr-code-generator.com/)
- [QRCode Monkey](https://www.qrcode-monkey.com/)

---

## 🎨 PERSONALIZZAZIONE

### Cambiare Colori
Modifica in `index.html` (e `dashboard.html`):

```css
:root{
  --primary:#2D3748;    /* Blu scuro */
  --secondary:#7DD3FC;   /* Azzurro */
}
```

### Aggiungere Lingua
In `index.html`, aggiungi nella sezione `TRANSLATIONS`:

```javascript
const TRANSLATIONS = {
  // ... existing languages
  fr: {
    'house': 'La maison',
    'wifi': 'Wi-Fi',
    // ... altre traduzioni
  }
}
```

### Coordinate per Meteo
Trova le coordinate su [LatLong.net](https://www.latlong.net/):
1. Cerca indirizzo
2. Copia lat/lon
3. Inserisci nel JSON

---

## 📊 TRACKING & ANALYTICS

### Dati Raccolti (localStorage per demo):

**Visite:**
```javascript
{
  apartment: "papaya",
  timestamp: "2025-10-08T14:32:00Z",
  source: "QR Code",
  userAgent: "...",
  language: "it"
}
```

**Feedback:**
```javascript
{
  rating: 5,
  name: "Mario Rossi",
  comment: "Bellissimo!",
  apartment: "papaya",
  timestamp: "2025-10-08T16:00:00Z"
}
```

### Produzione (TODO):
Per uso reale, sostituire localStorage con:
- **Firebase** (gratuito, facile)
- **Supabase** (open source)
- **API custom** (PHP/Node.js)

---

## 🔐 SICUREZZA DASHBOARD

### Cambio Password:
Modifica in `dashboard.html`:

```javascript
const DEMO_CREDENTIALS = {
  email: 'tua-email@email.com',
  password: 'tuaPasswordSicura123'
};
```

⚠️ **IMPORTANTE:** Per produzione usa autenticazione vera (Firebase Auth, Auth0, etc.)

---

## 🌐 DOMINIO PERSONALIZZATO

### Con GitHub Pages:
1. Acquista dominio (es: `qrelaxing.com`)
2. Aggiungi DNS record:
   ```
   Type: CNAME
   Name: www
   Value: tuonome.github.io
   ```
3. Su GitHub: Settings → Pages → Custom domain

### Alternative Hosting:
- **Netlify** (deploy automatico da GitHub)
- **Vercel** (stesso di Netlify)
- **Cloudflare Pages** (veloce e gratis)

---

## 📱 GENERARE QR CODE

### Online:
1. Vai su [QR Code Generator](https://www.qr-code-generator.com/)
2. Inserisci URL: `https://tuosito.github.io/qrelax?apt=NOME&source=qr`
3. Personalizza design
4. Scarica PNG/SVG

### Da stampare:
- **Formato consigliato:** 5x5 cm minimo
- **Materiale:** Adesivo plasticato
- **Posizione:** Ingresso, frigo, tavolo

---

## 💡 BEST PRACTICES

### Per Host:
- ✅ Aggiorna dati regolarmente
- ✅ Rispondi ai feedback
- ✅ Testa QR code prima di stampare
- ✅ Controlla statistiche settimanalmente

### Per Ospiti:
- ✅ WiFi sempre visibile
- ✅ Check-in/out chiari
- ✅ Emergenze in evidenza
- ✅ Massimo 5 ristoranti consigliati

### SEO:
- ✅ Nome appartamento nel title
- ✅ Alt text su tutte le immagini
- ✅ Meta description personalizzata

---

## 🐛 TROUBLESHOOTING

### "Errore nel caricamento dei dati"
- Verifica che il file JSON esista
- Controlla sintassi JSON su [JSONLint](https://jsonlint.com/)
- Nome file deve corrispondere al parametro `?apt=`

### Meteo non funziona
- Verifica coordinate lat/lon nel JSON
- Controlla connessione internet
- API Open-Meteo potrebbe essere temporaneamente offline

### QR code non funziona
- Testa URL nel browser prima
- Assicurati che GitHub Pages sia attivo
- Aspetta 5-10 minuti dopo publish

### Dashboard non mostra dati
- Controlla credenziali login
- Verifica che ci siano visite registrate
- Apri console browser per errori (F12)

---

## 📈 ROADMAP FUTURE

- [ ] Backend con database reale
- [ ] App mobile nativa
- [ ] Sistema prenotazioni integrato
- [ ] Pagamenti online
- [ ] Chat live con host
- [ ] Multi-proprietà per singolo host
- [ ] Export dati CSV/PDF
- [ ] Integrazione calendar (Airbnb, Booking)

---

## 📞 SUPPORTO

Per domande o problemi:
- **Email:** leonardo@qrelaxing.com
- **GitHub Issues:** [Link al tuo repo]

---

## 📄 LICENZA

Copyright © 2025 QRelax. Tutti i diritti riservati.

---

**Versione:** 2.0  
**Ultimo aggiornamento:** 08 Ottobre 2025