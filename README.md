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

Tutte derivate dagli asset del repo del gioco — non modificarle a mano qui, si rigenerano:

| File | Da dove viene |
|---|---|
| `img/hero.webp` | **composizione**: `assets/ui/menu_bg/tetto_alba.png` (1920×800, il tetto all'alba coi due piccioni) con sopra `assets/ui/menu_logo.png` scalato a 768 px con LANCZOS e centrato nel cielo a y=117. Il logo è arte a risoluzione piena, con dettagli da 1 px: **non** è pixel art da ingrandire col nearest |
| `img/logo-256.png`, `apple-touch-icon.png`, `favicon-64.png` | `iOS/icon.png` (il gatto che dorme di SU-366), ridotta a 256/180/64 px |
| `img/shot-menu.webp` | **scatto fresco** dal gioco: `bash tools/autotest/shot_su416.sh <dir> desktop_1280x720` produce `desktop_1280x720_5_menu.png` a 1280×720 nativi, convertito in WebP q88 senza ridurre. La lingua si impone scrivendo `lingua="en"` in `[general]` di un `settings.cfg` nella user-dir **isolata** del provino (`/tmp/su_<uid>_home_godot/Library/Application Support/Street University/`): quella vera di Ivan non si tocca e resta `it` |
| `img/shot-city-*.webp`, `shot-cards.webp`, `shot-shack.webp` | screenshot `STORE_ASSETS/google_play/screenshots/tablet_10` 2560×1440, ridotti 2:1 con filtro BOX a 1280×720, WebP q88. ⚠️ Sono della **versione vecchia**: `shot-shack.webp` in particolare mostra una UI che non esiste più così (la baracca è passata sotto PROGRESS) |

Il titolo del gioco vive **dentro** l'immagine dell'eroe: per questo l'`<h1>` della pagina è
`sr-only`, presente per lettori di schermo e motori di ricerca ma non disegnato due volte.

## Attenzione

- La **privacy policy** NON sta qui: vive nel repo `street-university-beta-devices` ed è
  l'URL già depositato presso Google Play e App Store Connect. Non spostarla.
- Il record DNS `TXT` di Epic e i record `MX` di iCloud stanno su **Cloudflare**: toccare i
  record `A`/`CNAME` del sito non deve mai toccare quelli della posta.
