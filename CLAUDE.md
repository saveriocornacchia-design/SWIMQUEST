# CLAUDE.md — Cloro Power

App PWA per l'allenamento di giovani nuotatori agonisti (10-14 anni). Pubblicata con GitHub Pages da `main`:
https://saveriocornacchia-design.github.io/SWIMQUEST/

## Architettura
- **Un solo file**: tutta l'app è in `index.html` (HTML + CSS + JS inline). Niente build, niente framework, niente dipendenze npm.
- **Nessuna API, nessun server**: i dati restano nel browser (`localStorage`). Non proporre backend, login o scraping (FIN, AQT Swim: già valutati e scartati).
- Manifest PWA e icone sono `data:` URI base64 dentro `index.html`.

## Regole che NON si violano
- **Chiavi localStorage invariate**: `swimquest_v5` (stato) e `swimquest_theme` (tema). Rinominarle = gli utenti perdono tutti i dati. Il nome "SwimQuest" nelle chiavi e nell'URL resta anche se l'app si chiama Cloro Power.
- **Non rinominare il repo**: cambierebbe l'URL di GitHub Pages e romperebbe i link già condivisi.
- Se cambia la struttura dello stato, aggiungere una migrazione in `loadState()` invece di cambiare chiave.
- Nessun dato personale hardcoded: nome, sesso, anno, giorni di allenamento e tempi li inserisce l'utente all'onboarding.
- Il protocollo alimentare è basato su dati fittizi: l'avviso in `#sec-food` deve restare.

## Logica principale (dove guardare)
- Onboarding/impostazioni: `openSettings()`, `obStep()`, `saveSettings()` — step 1 profilo, step 2 giorni in vasca.
- Categoria FIN: `finCategory(sesso, anno)`, `FIN_CATS`, `seasonEndYear()` (stagione da 1 ottobre).
- Giorni allenamento: `S.trainDays` (7 booleani, lunedì = 0); giorni non selezionati = off-water (`owPlan()`).
- Tempi: il primo tempo per stile è la baseline, obiettivo = baseline − 2s (`base()`, `tgt()`).
- XP anti-farming: `awardOnce(id, n)` — ogni azione dà XP una sola volta al giorno. Streak: `markActive()` / `checkStreak()` su giorni consecutivi di attività.
- Nomi nei testi: `{N}` / `{NU}` sostituiti da `withName()`; escape HTML con `esc()`.
- Tema chiaro/scuro: variabili CSS su `:root`, override `:root[data-theme="light"]`. Usare sempre le variabili, mai colori hardcoded.

## Flusso di lavoro
- Modifiche su branch di lavoro → test → merge su `main` (main = versione live).
- Testare con Playwright a larghezza telefono (360-390px): zero errori JS, onboarding completo, tema chiaro e scuro.
- Testi dell'interfaccia e README in **italiano**.
- Aggiornare il README quando cambiano funzionalità visibili.

## Licenza
Tutti i diritti riservati (vedi `LICENSE`). Non aggiungere licenze open source.
