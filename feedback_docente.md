# Feedback Docente – Sensori Meteo Backend

Gruppo: Sescu – Giatti – Malachin – Cosmi

---

## 1. Analisi dei Requisiti

* Non è specificato quali regole il backend deve applicare per strutturare, validare e arricchire i dati provenienti dai sensori (schema minimo, timestamp di ricezione, normalizzazione).
* Non è definita la politica di gestione di dati anomali, duplicati o in ritardo (scarto, marcatura, versioning), rendendo non verificabile la coerenza dello storico.
* Non sono esplicitati i requisiti di storicizzazione e disponibilità del dato (periodo di conservazione, granularità minima, tempi di accesso), rendendo il requisito di storicizzazione non misurabile.

## 2. Analisi Funzionale

* Mancano casi d’uso funzionali lato backend (ingestione, validazione, salvataggio, disponibilità dei dati verso sistemi esterni) descritti come flussi con input, output ed errori, rendendo il comportamento del sistema implicito e non verificabile.
* Non è descritto il comportamento funzionale del backend in caso di errori di ingresso (dati incompleti, fuori range, perdita di connessione), quindi non è chiaro come il sistema reagisce agli scenari anomali.
* Non è chiarito funzionalmente come il backend gestisce la temporalità del dato (campionamento, invio, ricezione) e l’allineamento dei timestamp, quindi non è definito cosa viene considerato dato in tempo reale e cosa storico.

---

## 3. Analisi Tecnica

*(valutazione indicativa)*

* Non è esplicitata l’architettura tecnica del backend né lo schema dati (schema logico + modello ER), quindi non sono valutabili componenti/responsabilità e coerenza della persistenza rispetto ai requisiti.
* Non sono definite le interfacce di integrazione e il formato dei messaggi (es. MQTT/HTTP, payload, mapping campi → metriche), quindi non è verificabile il percorso end-to-end dal gateway/ThingsBoard alla persistenza.
* Non sono specificate le scelte tecniche per garantire affidabilità e continuità del backend (gestione perdita dati, persistenza sicura, recupero dopo fault), quindi non è valutabile la robustezza del sistema nel tempo.

---

## Nota metodologica finale

Il documento mostra una buona comprensione del dominio applicativo e degli obiettivi generali del sistema, ma soffre di una separazione non sempre netta tra requisiti, funzionalità e scelte tecniche. In un contesto progettuale o lavorativo, è fondamentale isolare chiaramente cosa il sistema deve garantire (requisiti), come si comporta dal punto di vista logico-funzionale (funzionale) e come viene realizzato concretamente (tecnica).

L’assenza iniziale di questa distinzione rende più difficile valutare completezza, verificabilità e coerenza dell’architettura backend. La riorganizzazione incrementale delle osservazioni va nella direzione corretta e costituisce una base solida per una successiva revisione progettuale più strutturata.
