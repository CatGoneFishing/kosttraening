# Næringsdagbog

En personlig kost-, vægt- og træningsdagbog. Statisk web-app – ingen server, ingen build-trin. Al data gemmes lokalt i din browser (localStorage) på den enhed, du bruger den fra.

## Sådan lægger du den på GitHub Pages

1. Opret et nyt, offentligt repository på GitHub (fx `naeringsdagbog`).
2. Upload alle filerne i denne mappe til roden af repositoriet:
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - `icon-192.png`
   - `icon-512.png`
3. Gå til repositoriets **Settings → Pages**.
4. Under "Build and deployment" vælger du **Source: Deploy from a branch**, branch **main**, mappe **/ (root)**. Gem.
5. Efter et minuts tid er siden tilgængelig på `https://DIT-BRUGERNAVN.github.io/naeringsdagbog/`.

## Sådan får du den som en app på telefonen

**iPhone (Safari):**
Åbn linket → tryk på Del-ikonet (firkant med pil op) → "Føj til hjemmeskærm".

**Android (Chrome):**
Åbn linket → tryk på de tre prikker øverst til højre → "Føj til startskærm" / "Installer app".

Herefter åbner den som en almindelig app, uden browserens adresselinje.

## Vigtigt om data

- Al data (log, vægt, mål, favoritter osv.) gemmes **kun lokalt i browseren på den enhed og i den browser**, du bruger. Der er intet centralt gemt hos GitHub eller andre.
- Rydder du browserdata/cache for siden, eller skifter du browser/telefon, mister du adgangen til dataen **medmindre** du har eksporteret den først.
- Brug appens **Eksporter data** (under Mål) jævnligt som backup, og ved telefonskifte – importér filen igen på den nye enhed via **Importer data**.
- Slet aldrig "Website Data" / "Storage" for din github.io-side i browserindstillingerne uden at have eksporteret først.

## Funktioner der kræver internet

- Søgning og stregkodescanning slår op i Open Food Facts (kræver forbindelse).
- Alt andet (logning, redigering, grafer, mål) virker offline, når siden først er indlæst én gang (takket være service workeren i `sw.js`).

## Filoversigt

| Fil | Formål |
|---|---|
| `index.html` | Selve appen |
| `manifest.json` | Gør siden installerbar som app (PWA) |
| `sw.js` | Offline-cache af app-filerne |
| `icon-192.png`, `icon-512.png` | App-ikoner til hjemmeskærm |
