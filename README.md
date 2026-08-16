# streetuniversitygame.com

Sito pubblico di **Street University** — una pagina sola, statica, servita da GitHub Pages
sul dominio `streetuniversitygame.com`.

## Perché esiste

Tre motivi, in ordine di urgenza:

1. **Brand Review di Epic Account Services.** Per far loggare i beta tester col loro account
   Epic serve la Brand Review approvata, che vuole una *Domain Verification* (record DNS TXT
   sul dominio) e un dominio pubblico che porti **nome dell'organizzazione, nome e descrizione
   del prodotto**. Su `*.github.io` la verifica è impossibile: il DNS è di GitHub.
   Questo sito è il dominio verificabile.
2. **Application Website** da dichiarare nel Dev Portal di Epic.
3. Un posto pubblico dove mandare chi chiede del gioco.

## Cosa c'è dentro

| File | Cosa |
|---|---|
| `index.html` | tutta la pagina: HTML + CSS inline, **nessuna richiesta a terzi** (niente font, CDN, analytics) |
| `img/` | grafiche derivate da `STORE_ASSETS/google_play/` del repo del gioco |
| `CNAME` | il dominio personalizzato, letto da GitHub Pages |

La pagina è bilingue **EN/IT**: con JavaScript attivo compare il selettore e si vede una lingua
sola; senza JavaScript si vedono entrambe, una sotto l'altra. Non si rompe mai.

Il testo inglese è lo **stesso** della scheda Google Play (`DISTRIBUZIONE_STORE.md` §7.4):
se cambia una delle due, vanno allineate a mano. La versione italiana è nata qui.

## Come si aggiorna

Commit e push su `main`. GitHub Pages ricostruisce da sé in un paio di minuti.

## Immagini

Rigenerate dal repo del gioco (non modificarle a mano qui):
screenshot `tablet_10` 2560×1440 ridotti 2:1 con filtro BOX a 1280×720 e salvati in WebP q88;
`feature_graphic_1024x500.png` in WebP q90; `icon_512.png` ridotta a 256/180/64 px.

## Attenzione

- La **privacy policy** NON sta qui: vive nel repo `street-university-beta-devices` ed è
  l'URL già depositato presso Google Play e App Store Connect. Non spostarla.
- Il record DNS `TXT` di Epic e i record `MX` di iCloud stanno su **Cloudflare**: toccare i
  record `A`/`CNAME` del sito non deve mai toccare quelli della posta.
