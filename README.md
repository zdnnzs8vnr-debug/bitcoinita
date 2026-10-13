# GUSTAVOEURO — Portale Dark-Web / Hacker

Sito **single-page** per il business GUSTAVOEURO: banconote Euro Grade AAA+
e trasferimenti PayPal P2P anonimi. Nessun build step: apri `index.html` e funziona.

---

## Listino (blocco `PRODUCTS` in `index.html`)

| Taglio | Pezzi | €/pezzo | Totale |
|---|---|---|---|
| 20 EUR | 30 | 8 | 240 |
| 20 EUR | 50 | 7,5 | 375 |
| 20 EUR | 75 | 7 | 525 |
| 20 EUR | 100 | 6,5 | 650 |
| 20 EUR | 150 | 5,8 | 870 |
| 20 EUR | 200 | 5 | 1000 |
| 50 EUR | 30 | 12 | 360 |
| 50 EUR | 50 | 11 | 550 |
| 50 EUR | 75 | 9,5 | 712,50 |
| 50 EUR | 100 | 8,5 | 850 |
| 50 EUR | 150 | 7,8 | 1170 |
| 50 EUR | 200 | 7 | 1400 |

Taglio 10 EUR: su richiesta (foto `note10.png`).

## Transfer PayPal (blocco `PAYPAL`)

120→360 · 150→680 · 180→930 · 220→1570 · 280→2140 · 320→3400 · 380→4800 · 470→5800

## Bonifico istantaneo
IBAN `IT62A0366901600560522253386` — intestatario `GIUSEPPE DI VICO` (+10%).

## Spedizioni (blocco `SHIPPING`)
- `priv` — Corriere privato, **20 €**, solo Italia, 12/48h, rimborso completo se in ritardo.
- `locker` — Locker InPost, **incluso**, indirizzo locker inserito dal cliente.
  Cambia il prezzo in `SHIPPING.locker.price` se serve.

## Pagamento
Dopo **INVIA ORDINE** l'ordine resta in stato **IN REVISIONE**: il pagamento non è
ancora rilevato. Appena il bot lo rileva, il pacco parte entro 1-2 ore.

## Feedback
Chi vuole leggere i feedback va sul canale: https://t.me/+gBf54xWnFapjMmRh

---

## File

**Principali:** `index.html`, `_headers`, `.htaccess`, `404.html`, `.nojekyll`, `robots.txt`
**Protezione:** `_redirects`, `nginx.conf`, `netlify.toml`, `vercel.json`, `Caddyfile`,
`firewall.conf`, `ipset-block.sh`, `sitemap.xml`, `.well-known/security.txt`,
`humans.txt`, `manifest.webmanifest`, `sw.js`, `README.md`

## Da aggiungere accanto a `index.html`
`note10.png` · `qr-sol.png` · `qr-btc.png` · `qr-ltc.png` · opzionali `icon-192.png`, `icon-512.png`.
Se `note10.png` manca, si attiva la catena di fallback e in ultima istanza una
banconota 10 EUR disegnata in SVG: **mai icona rotta**.

## Personalizzare (10 secondi)
In cima allo script: `PHOTO` (foto), `PRODUCTS` (listino), `PAYPAL` (transfer),
`SHIPPING` (spedizioni), `COINS` (indirizzi crypto), `IDENT` (IBAN, Telegram, PGP).

## Deploy
- **GitHub Pages:** carica in root. `_headers`/`_redirects`/`.htaccess` ignorati →
  metti **Cloudflare in proxy** davanti al dominio per header + IP nascosto.
- **Netlify / Cloudflare Pages / Vercel:** config già pronte.
- **VPS:** `nginx.conf` + `firewall.conf` (o `Caddyfile`).
  Firewall: `sudo ./ipset-block.sh install && sudo ./ipset-block.sh watch`

© GUSTAVOEURO · dal 2022
