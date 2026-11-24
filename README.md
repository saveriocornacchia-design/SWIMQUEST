# SwimQuest 🏊

App web per giovani nuotatori agonisti: registra i tempi, segue i progressi verso l'obiettivo e motiva con XP, livelli e trofei.

**Apri l'app:** https://saveriocornacchia-design.github.io/SWIMQUEST/

## Funzioni

- **Profilo**: al primo avvio si inseriscono nome, avatar, sesso e anno di nascita. La categoria FIN (Esordienti B1/B2, A1/A2, Ragazzi, Juniores, Cadetti) viene calcolata in automatico per la stagione in corso, che parte il 1° ottobre. Si modifica da ⚙️.
- **Giorni di allenamento**: subito dopo il profilo si scelgono i giorni in piscina; gli altri diventano off-water, con le sessioni assegnate in automatico (Potenziamento A/B alternati, Elasticità l'ultimo giorno off-water della settimana). Si modificano da ⚙️.
- **Tempi**: registrazione di tempi di allenamento e di gara ufficiale, storico e record personali. Il primo tempo registrato per ogni stile diventa il tempo di partenza; l'obiettivo è la partenza −2 s.
- **Off-Water**: piano settimanale di potenziamento ed elasticità con checklist.
- **Cibo**: piano pasti del giorno e checklist giornaliera. Il protocollo alimentare è basato su dati fittizi: per modificarlo contattare l'amministratore.
- **Mente & Gara**: umore, respirazione 4-7-8, visualizzazione e diario pre-gara.
- **XP e streak**: ogni azione dà XP una sola volta al giorno, quindi togliere e rimettere una spunta non dà altri punti. La streak conta i giorni consecutivi con almeno un'attività e si azzera se ne salti uno.
- **Tema chiaro/scuro**: pulsante ☀️/🌙 nell'header; la scelta viene ricordata.

## Installazione sul telefono

- **iPhone (Safari)**: Condividi ↑ → *Aggiungi a schermata Home*.
- **Android (Chrome)**: menu ⋮ → *Installa app* (oppure il banner che compare in alto).

## Dati

Non ci sono server né account: tutto è salvato nel browser del telefono (localStorage).

- Ogni telefono o browser ha i propri dati.
- Cancellare i dati del browser cancella anche quelli dell'app, e non c'è un backup.

## Sviluppo

L'app è un solo file statico, `index.html`, senza build né dipendenze. GitHub Pages lo pubblica dal branch `main`. Per provarla in locale basta aprire il file nel browser.

## Licenza

Tutti i diritti riservati: vedi [LICENSE](LICENSE). L'app si può usare dal link, ma non copiare, modificare o ripubblicare senza permesso.
