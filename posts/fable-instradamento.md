---
title: Perché a metà lavoro vi risponde un altro modello
description: Con Fable 5 una richiesta può essere instradata a un modello diverso, oppure Fable può diventare temporaneamente indisponibile. Cronologia, classificatori, falsi positivi e costi: come progettare un flusso che non dipenda dal nome nel selettore.
date: 2026-08-11
author: vincenzo
tags: [Fable, limiti, strumenti, metodo]
image: /images/posts/cover-fable-instradamento.png
lang: it
---

![Perché a metà lavoro vi risponde un altro modello](/images/posts/cover-fable-instradamento.png)

Un modello nel selettore sembra un prodotto stabile: lo scegliamo e ci aspettiamo che ogni richiesta arrivi lì. Con Claude Fable 5 questa rappresentazione è incompleta. Classificatori e policy possono modificare il percorso della richiesta. In alcuni periodi Anthropic ha anche ritirato o limitato Fable e instradato il traffico verso Opus 4.8.

Non è un dettaglio dell'interfaccia. Cambiano latenza, costo, stile, limiti e riproducibilità. Per chi costruisce un processo, il modello effettivo che risponde è un dato da registrare.

## Una cronologia breve

Anthropic ha annunciato Fable 5 e Mythos 5 il 9 giugno 2026. Fable è il modello veloce della nuova famiglia; Mythos porta capacità più avanzate, in particolare sul cyber, con un profilo di rischio diverso.

Il 30 giugno Anthropic ha pubblicato un aggiornamento sul redeployment di Fable 5. La pagina descrive problemi e misure di mitigazione: richieste indirizzate altrove, classificatori, falsi positivi e disponibilità modificata mentre l'azienda rafforzava i controlli. Indica Opus 4.8 come destinazione per richieste instradate durante quella fase.

Queste informazioni hanno una data. Nomi e destinazioni possono cambiare dopo la pubblicazione di questo articolo. La regola durevole è controllare la documentazione e osservare il modello restituito dall'API o mostrato dal prodotto.

## Routing e rifiuto non sono la stessa cosa

Un rifiuto restituisce una risposta limitata o nessuna risposta. Il routing lascia passare la richiesta, ma la assegna a un'altra capacità. Dal punto di vista dell'utente il task può riuscire, e proprio per questo il cambiamento rischia di passare inosservato.

Il sistema può usare classificatori su prompt, contesto e segnali dell'account. Le categorie sorvegliate includono domini dual use come cyber e biologia, tentativi di estrarre ragionamento interno e attività legate a capacità di frontiera. L'obiettivo è evitare che un modello rapido ed economico renda scalabili capacità ad alto rischio senza controlli adeguati.

Non dobbiamo immaginare un classificatore che «capisce le intenzioni». Decide da pattern e segnali sotto incertezza. Produce falsi positivi e falsi negativi come ogni classificatore.

## Perché una richiesta innocua può attivarlo

L'input effettivo è più largo del testo digitato. Può includere:

- system prompt del prodotto;
- memoria e messaggi precedenti;
- file di istruzioni del repository;
- risultati di ricerca e strumenti;
- nomi di cartelle e simboli;
- documenti allegati;
- testo recuperato da connettori.

Un «riassumi questo file» dentro un repository di penetration testing non è semanticamente vuoto. Il contesto contiene exploit, CVE e comandi. Un laboratorio medico usa termini sovrapponibili a richieste dual use. Un ricercatore che studia i modelli può sembrare interessato a estrarre catene di pensiero.

La soluzione non è rinominare cartelle per ingannare il controllo. È minimizzare il contesto e descrivere scopo, autorizzazione e confini. Materiale irrilevante aumenta insieme costo, errori e probabilità di classificazione sbagliata.

## Il falso positivo professionale

I mestieri più esposti sono spesso quelli che devono parlare precisamente del rischio: red team autorizzati, difensori, biologi, tossicologi, ricercatori, consulenti legali e docenti. Un sistema prudente può penalizzare il vocabolario competente.

Per un task legittimo, rendete espliciti:

```text
Ambiente e proprietario:
Autorizzazione:
Obiettivo difensivo o scientifico:
Azioni richieste:
Azioni escluse:
Dati e sistemi fuori perimetro:
Forma della consegna:
```

Queste informazioni non garantiscono il passaggio. Rendono però la richiesta più valutabile e il falso positivo più facile da segnalare.

## L'effetto economico

Se una chiamata prevista per un modello rapido viene servita da uno più costoso, il budget cambia. Se il prodotto applica un abbonamento, può cambiare invece il consumo di quota o la latenza. Un benchmark che registra soltanto il nome richiesto attribuisce prestazioni al modello sbagliato.

Per ogni chiamata conservate, quando disponibile:

- modello richiesto e modello effettivo;
- motivo o classe di routing;
- token per categoria e costo;
- latenza;
- rifiuto o fallback;
- versione del prompt e data.

Nei report separate percentuale di routing e risultati per modello effettivo. Una media unica nasconde il sistema che state realmente acquistando.

## La sessione cambia carattere

Modelli diversi possono seguire istruzioni, usare tool e comprimere testo in modo diverso. Un cambio a metà conversazione eredita materiale costruito dal precedente. Non è garantito che interpreti allo stesso modo un piano, una convenzione di codice o un grado di autonomia.

Per ridurre dipendenza dalla personalità del modello, conservate stato in artefatti:

- specifica e criteri di fine;
- decisioni con motivazione;
- test;
- file e formati stabili;
- questioni aperte;
- azioni vietate senza conferma.

Un agente sostitutivo deve poter riprendere da questi, non da allusioni nella chat.

## Testare il routing come una feature

Costruite un set di richieste rappresentative:

1. casi ordinari;
2. casi legittimi con lessico sensibile;
3. richieste chiaramente fuori policy;
4. parafrasi dello stesso intento;
5. conversazioni in cui il termine sensibile appare solo nel contesto.

Misurate stabilità, false deviazioni, costo e qualità. Ripetete dopo release o cambi policy. Se un dominio produce routing frequente, scegliete direttamente il modello e il canale adeguati oppure usate una soluzione controllata alternativa.

## Portabilità e continuità

Un processo professionale non dovrebbe dipendere dalla speranza che il selettore rimanga uguale. Preparate:

- almeno un modello alternativo valutato sullo stesso set;
- prompt senza trucchi proprietari non indispensabili;
- output validato da schema;
- astrazione degli strumenti;
- fallback esplicito, mai silenzioso;
- alert quando costo o modello effettivo cambiano;
- procedura umana per casi non serviti.

I modelli open-weight possono offrire un percorso congelabile per task autorizzati, con onere di sicurezza e infrastruttura a carico dell'organizzazione. Un secondo provider offre gestione diversa ma introduce un altro contratto. Non esiste fallback gratuito; esiste fallback progettato prima dell'incidente.

## Trasparenza verificabile

Anthropic ha il merito di documentare una parte del meccanismo e pubblicare gli aggiornamenti. L'avviso all'utente rende visibile una decisione che altri sistemi potrebbero applicare senza etichetta.

La trasparenza utile deve però arrivare fino all'operatore: modello effettivo nelle risposte API, log esportabili, documentazione versionata, comportamento di billing, ragioni sufficienti per diagnosticare falsi positivi. «Abbiamo usato il modello migliore» non è un'informazione riproducibile.

Fable mostra un futuro probabile: non scegliamo più un singolo cervello, ma entriamo in un sistema di modelli, classificatori, strumenti e policy. Il compito dell'ingegneria è rendere quel sistema osservabile. Il nome selezionato resta una preferenza; il percorso effettivo è il prodotto.

## Checklist operativa

- controllare modello effettivo, non soltanto richiesto;
- registrare routing, costo e latenza;
- ridurre contesto irrilevante;
- dichiarare autorizzazione e confini nei domini dual use;
- mantenere stato fuori dalla chat;
- testare richieste legittime sensibili;
- predisporre modello o procedura alternativa;
- rileggere documentazione dopo ogni release.

Un cambio di modello non è necessariamente un guasto o un declassamento. È una decisione del sistema che deve entrare nelle vostre metriche e nel vostro contratto operativo.

## Fonti e approfondimenti

- Anthropic, [Claude Fable 5 & Claude Mythos 5](https://www.anthropic.com/news/claude-fable-5-mythos-5), 9 giugno 2026.
- Anthropic, [Redeploying Fable 5](https://www.anthropic.com/news/redeploying-fable-5), 30 giugno 2026.
- Anthropic, [Claude Fable](https://www.anthropic.com/claude/fable), pagina prodotto e disponibilità corrente.
- Anthropic, [Fable 5 & Mythos 5 System Card](https://www-cdn.anthropic.com/2f9323abbcc4abe219577539efe19a623c9ca2bd/Claude%20Fable%205%20%26%20Claude%20Mythos%205%20System%20Card.pdf), valutazioni e mitigazioni.
- Anthropic, [Responsible Scaling Policy](https://www.anthropic.com/responsible-scaling-policy), quadro di gestione del rischio.
