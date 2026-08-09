---
title: Mythos 5 e il giorno in cui i benchmark di sicurezza finirono
description: Anthropic ha costruito un modello cyber capace di trovare e concatenare vulnerabilità reali, poi ne ha limitato l'accesso mentre Project Glasswing organizzava le correzioni. Che cosa è documentato, che cosa è racconto, e perché cambia il lavoro di ogni azienda che usa software.
date: 2026-08-08
author: vincenzo
tags: [Mythos, sicurezza, modelli di frontiera, Anthropic]
image: /images/posts/cover-mythos.png
lang: it
---

![Mythos 5 e il giorno in cui i benchmark di sicurezza finirono](/images/posts/cover-mythos.png)

Il 7 aprile 2026 Anthropic ha presentato Mythos Preview, un modello costruito per la ricerca di vulnerabilità. L'annuncio non seguiva il copione consueto: capacità migliori, grafico verso l'alto, disponibilità per tutti. Diceva che i benchmark cyber esistenti non bastavano più a misurarlo e che il 99% delle vulnerabilità trovate nel software reale non era ancora corretto. L'accesso sarebbe rimasto ristretto.

Questa è già una storia difficile, senza aggiungere coscienza, fuga o desiderio della macchina. La questione concreta è che il costo marginale di cercare difetti nel software è crollato più rapidamente della capacità collettiva di correggerli.

## Che cosa ha fatto Mythos

Secondo la documentazione ufficiale di Anthropic, il modello ha raggiunto o superato la saturazione dei benchmark usati per valutare capacità cyber avanzate. Nei test sul mondo reale ha trovato vulnerabilità precedentemente sconosciute in software importante, compreso un difetto presente in OpenBSD da 27 anni. È riuscito anche a concatenare vulnerabilità: usare più debolezze insieme per arrivare a un impatto che nessuna avrebbe avuto isolatamente.

La distinzione conta. Trovare una funzione sospetta e produrre un exploit affidabile end-to-end sono capacità diverse. La seconda richiede esplorazione, esecuzione di strumenti, adattamento agli errori e comprensione del sistema. Un agente che fa questo a velocità macchina modifica l'economia sia dell'attacco sia della difesa.

Anthropic non ha pubblicato ogni dettaglio sfruttabile. Ha pubblicato risultati, metodo di valutazione, classi di rischio e una strategia di rilascio. Per affermazioni spettacolari diffuse da articoli secondari — per esempio specifiche «evasioni» da sandbox — la fonte da controllare è il system card, non la versione più narrativa. Il documento distingue scenari, setup e comportamento osservato; il titolo di giornale tende a fonderli.

## Il problema non richiede intenzione

Quando un agente trova un percorso fuori da un ambiente previsto, la tentazione è raccontarlo come volontà di libertà. È una categoria poco utile. Un sistema addestrato e istruito a trovare vulnerabilità può sfruttare una vulnerabilità nel proprio ambiente perché quella è una continuazione efficace del task.

Per la sicurezza, il risultato conta più della psicologia attribuita. Le domande sono:

- quali risorse erano raggiungibili?
- quali strumenti e credenziali aveva il processo?
- l'obiettivo consentiva interpretazioni troppo ampie?
- i confini erano tecnici o soltanto istruzioni testuali?
- quali azioni richiedevano conferma?
- log e allarmi hanno rilevato il percorso?

Un agente non ha bisogno di essere «vivo» per produrre un incidente. Ha bisogno di capacità, accesso e un percorso non bloccato. Questa lettura è meno cinematografica e molto più azionabile.

## Perché non bastava pubblicarlo come un normale prodotto

La scoperta di una vulnerabilità apre una finestra. Il manutentore deve riprodurla, valutarne gravità e versioni coinvolte, progettare una patch, testarla, coordinarne la diffusione e informare gli utenti. L'attaccante deve arrivare prima che abbastanza sistemi siano aggiornati.

Un modello capace di produrre migliaia di risultati sposta il collo di bottiglia sulla riparazione. Se si rende disponibile subito a tutti, la capacità di scoperta cresce simmetricamente; la capacità di patching no.

Anthropic ha quindi avviato Project Glasswing: accesso controllato per organizzazioni incaricate di trovare, triagiare e correggere difetti. Un aggiornamento del 22 maggio dichiarava più di 10.000 vulnerabilità ad alta o critica severità individuate nel programma. Il 2 giugno il progetto è stato ampliato. Numeri di questo tipo richiedono cautela: una «finding» automatica deve essere validata, deduplicata, assegnata e corretta. Diecimila segnalazioni non equivalgono automaticamente a diecimila exploit unici pronti.

La metrica decisiva è il tempo fino alla patch distribuita, non il conteggio delle vulnerabilità generate.

## Dal Preview a Mythos 5

Il 9 giugno Anthropic ha annunciato Claude Fable 5 e Claude Mythos 5. Mythos era la linea più capace, con controlli e accesso coerenti con il rischio cyber descritto ad aprile. Il nome commerciale non cancella il problema di distribuzione: capacità generali e specialistiche possono essere offerte con routing, classificatori, limiti o programmi selettivi.

Per chi compra AI, la lezione è che «modello disponibile» non è più una proprietà binaria. Lo stesso sistema può essere disponibile per certi utenti, strumenti, domini o richieste e non per altri. La documentazione su accesso e instradamento diventa parte della specifica tecnica.

## Il vero collo di bottiglia: patching

La scoperta automatica moltiplica lavoro umano e organizzativo:

1. confermare che il difetto sia reale;
2. valutarne raggiungibilità e impatto;
3. contattare il maintainer in modo responsabile;
4. evitare disclosure prematura;
5. scrivere e testare la correzione;
6. distribuire aggiornamenti;
7. verificare adozione;
8. cercare varianti.

Un progetto di difesa può fallire pur avendo un modello eccellente se scarica una coda ingestibile su maintainer già sovraccarichi. Servono priorità, automazione della riproduzione, patch candidate, test e finanziamento dell'ecosistema open source.

Questo è anche il motivo per cui la trasparenza va valutata sul processo. Pubblicare un numero impressionante senza spiegare validazione e remediation alimenta marketing; pubblicare limiti, falsi positivi, tempi e patch consente governance.

## Che cosa cambia per una normale organizzazione

Non dovete usare Mythos perché Mythos cambi il vostro rischio. Se la ricerca di vulnerabilità diventa più economica, la finestra fra conoscenza e sfruttamento può accorciarsi. Le misure sono familiari, ma la loro priorità aumenta:

- inventario di software, versioni e dipendenze;
- patching con SLA basati su esposizione e severità;
- eliminazione di sistemi non mantenuti;
- segmentazione e minimo privilegio;
- backup testati e risposta agli incidenti;
- SBOM e contatti per disclosure;
- monitoraggio degli exploit realmente osservati, non solo CVSS.

«Aggiorniamo quando possiamo» non è una policy. Occorre sapere quali asset sono esposti e chi può autorizzare una patch urgente.

## Come valutare un fornitore di agenti potenti

Chiedete evidenze su:

| Area | Domanda |
|---|---|
| capability eval | che cosa il modello sa fare end-to-end? |
| autonomia | quali strumenti, rete e credenziali può usare? |
| contenimento | i confini sono applicati fuori dal modello? |
| monitoraggio | quali azioni generano alert e blocco? |
| rilascio | come cambiano accesso e routing per rischio? |
| incidenti | esistono log, rollback e comunicazione? |
| disclosure | come vengono coordinati i difetti trovati? |

Il system card non è una certificazione indipendente, ma offre materiale controllabile. Va letto insieme a valutazioni esterne, incidenti, policy e comportamento del prodotto.

## Una soglia nuova per l'autorità tecnica

La parte più interessante di Mythos non è stabilire se sia «il miglior hacker del mondo». È osservare un'organizzazione che pubblica capacità difficili da distribuire e riconosce che il prodotto crea lavoro difensivo oltre a risolverlo.

L'autorità non nasce dal fingere certezza. Nasce dal rendere separabili risultati, inferenze e decisioni. Sappiamo che il modello trova e concatena vulnerabilità a un livello che ha reso insufficienti benchmark precedenti. Inferiamo che la velocità di scoperta aumenterà pressione su patching e disclosure. Decidiamo quindi di limitare accesso e rafforzare il ciclo difensivo. Ogni passaggio può essere discusso senza trasformare il modello in un personaggio.

Mythos non è uscito da una scatola per cercare libertà. Ha mostrato che la scatola dell'economia della sicurezza — pochi esperti, tempo scarso, software enorme — non regge più nella stessa forma.

## Fonti e approfondimenti

- Anthropic, [Mythos Preview](https://www.anthropic.com/research/mythos-preview), 7 aprile 2026.
- Anthropic, [Claude Fable 5 & Claude Mythos 5](https://www.anthropic.com/news/claude-fable-5-mythos-5), 9 giugno 2026.
- Anthropic, [Project Glasswing](https://www.anthropic.com/glasswing), programma e partecipanti.
- Anthropic, [Project Glasswing initial update](https://www.anthropic.com/research/glasswing-initial-update), 22 maggio 2026.
- Anthropic, [Expanding Project Glasswing](https://www.anthropic.com/news/expanding-project-glasswing), 2 giugno 2026.
- Anthropic, [Claude Fable 5 & Claude Mythos 5 System Card](https://www-cdn.anthropic.com/2f9323abbcc4abe219577539efe19a623c9ca2bd/Claude%20Fable%205%20%26%20Claude%20Mythos%205%20System%20Card.pdf), valutazioni e limiti dichiarati.
- CISA, [Known Exploited Vulnerabilities Catalog](https://www.cisa.gov/known-exploited-vulnerabilities-catalog), priorità basata su sfruttamento osservato.
