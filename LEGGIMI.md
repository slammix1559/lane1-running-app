# LANE 1 — Preparazione podistica

App web installabile (PWA): un'unica cartella statica, nessun backend richiesto.

## Come metterla online (GitHub Pages, come le tue altre app)

1. Crea un repository su GitHub (es. `lane1-running-app`), pubblico.
2. Carica **tutto il contenuto di questa cartella** (index.html, bundle.js, manifest.json,
   service-worker.js, la cartella icons/) nella root del repository — non in una sottocartella.
3. Impostazioni del repo → Pages → Source: `Deploy from a branch`, branch `main`, cartella `/ (root)`.
4. Dopo qualche minuto sarà online su `https://<tuo-utente>.github.io/lane1-running-app/`.

## Come installarla sul telefono

- **Android/Chrome**: apri il link, tocca il menu ⋮ → "Aggiungi a schermata Home" (o comparirà
  da solo un banner di installazione). Da lì si apre a schermo intero come un'app vera.
- **iPhone/Safari**: apri il link, tocca l'icona di condivisione → "Aggiungi a Home".

## Cosa cambia rispetto alla versione artifact

- I dati (piano allenamento e storico) sono salvati con lo storage reale del browser
  (`localStorage`), non più legati a Claude: restano sul telefono anche a app chiusa.
- Il Service Worker mette in cache tutta l'app la prima volta che la apri: da quel momento
  builder e cockpit funzionano anche senza connessione (il GPS non ha comunque bisogno di rete).
- Bluetooth (per il cardio), GPS e sintesi vocale funzionano come su qualunque sito HTTPS —
  Chrome su Android li supporta tutti; Safari/iOS non supporta il Bluetooth via browser
  (limite di Apple, non dell'app).

## Nota sull'HTTPS

Sia GPS che Bluetooth richiedono che il sito sia servito in HTTPS. GitHub Pages lo fa
automaticamente, quindi non serve configurare nulla.
