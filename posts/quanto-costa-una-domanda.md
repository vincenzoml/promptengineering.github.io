---
title: Quanto costa una domanda
description: Il prezzo si misura in token, che non sono parole. Come si legge davvero una bolletta, perché i documenti lunghi costano più di quanto sembri, e dove va a finire il costo che conta — che non è quello.
date: 2026-05-12
author: vincenzo
tags: [costi, token, metodo]
image: /images/posts/cover-quanto-costa-una-domanda.png
lang: it
---

![Quanto costa una domanda](/images/posts/cover-quanto-costa-una-domanda.png)

Che cos'è un token e perché l'italiano ne consuma più dell'inglese; come si fa una stima di spesa che regga; il meccanismo per cui una conversazione lunga costa molto più della somma dei suoi messaggi; e la voce di costo vera, che nessun listino riporta.

Chi usa un abbonamento paga una cifra fissa e non ci pensa. Chi passa all'accesso via interfaccia di programmazione — perché deve automatizzare qualcosa, o perché lo strumento che usa funziona così — si trova davanti a un listino con dei numeri per milione, e la domanda diventa concreta: quanto costa, alla fine, una richiesta?

## Il token

L'unità di misura è il **token**, un frammento, anziché la parola intera. I modelli spezzano il testo in pezzi che a volte sono parole intere, più spesso sillabe o gruppi di lettere. "Intelligenza" può diventare tre o quattro token. I numeri si spezzano in modo capriccioso, la punteggiatura conta, gli spazi anche.

Una regola pratica per l'italiano: **circa un token ogni tre caratteri**, cioè grosso modo mille token ogni settecento parole. L'inglese rende un po' meglio, perché i vocabolari di questi sistemi sono stati costruiti soprattutto su quello: la stessa cosa detta in italiano costa fra il dieci e il trenta per cento in più di frammenti. È una tassa piccola e reale, che pesa solo su chi lavora a volume.

Si paga in ingresso e in uscita, con tariffe diverse: l'uscita costa più dell'ingresso, di solito tre o quattro volte. Il che ha una conseguenza operativa immediata — chiedere risposte concise non è solo una scelta di stile.

## Un conto vero

Una pagina di testo sono all'incirca cinquecento parole, cioè settecento token. Un contratto di venti pagine sta sui quattordicimila.

Ai prezzi correnti dei modelli di fascia alta, dare in pasto quel contratto e ricevere una sintesi di due pagine costa qualche centesimo. Con un modello leggero, una frazione di centesimo. Ripetuto su duecento contratti, siamo nell'ordine di qualche euro.

Il numero sorprende quasi tutti, e nella direzione opposta a quella che si aspettano: l'elaborazione costa molto meno di quanto la gente immagini. Un'analisi che a una persona costa un'ora costa alla macchina meno di un caffè.

## La trappola delle conversazioni lunghe

C'è però un meccanismo che fa saltare i conti, e va capito perché non è intuitivo.

A ogni messaggio, il modello rilegge **tutta** la conversazione da capo. Quindi il decimo messaggio non costa come il primo: costa come tutti i nove precedenti più sé stesso. In una chat lunga il costo cresce come il quadrato della lunghezza, non in proporzione.

Chi automatizza qualcosa senza saperlo si ritrova con una bolletta inspiegabile. Chi lo sa, spezza: una conversazione per pratica, chiusa quando la pratica è chiusa. È lo stesso consiglio che si dà per la qualità delle risposte, e per una volta le due esigenze puntano nella stessa direzione.

Stessa logica per i documenti allegati: se rimangono nel contesto, li ripagate a ogni messaggio. Chiedere una sintesi e proseguire su quella costa una frazione, e spesso funziona meglio.

## Il costo che conta

Detto tutto questo, per la maggior parte degli studi il costo dei token è rumore di fondo. Trenta euro al mese di abbonamento, o pochi euro di consumo: sono cifre che non entrano in nessuna decisione.

La voce di spesa vera è **il tempo di verifica**. Un documento prodotto in dieci secondi va comunque letto, controllato, corretto — e quel controllo lo fa una persona pagata. Se il testo esce bene e la revisione costa cinque minuti, avete guadagnato. Se esce plausibile ma sbagliato in modo sottile, e la revisione costa quaranta minuti di rilettura sospettosa, avete perso, per quanto la generazione sia costata zero.

È il calcolo che nessun listino riporta ed è l'unico che decide se lo strumento vi conviene. Da cui la conseguenza pratica: **investite nel far uscire bene la prima volta** — istruzioni scritte per bene, esempi, contesto — perché ogni minuto risparmiato lì vale mille volte il centesimo dei token.

## Leggere un listino senza sbagliare unità

Le API quotano di solito un milione di token, separando input e output. Alcune distinguono token letti dalla cache, scritti in cache, ragionamento o batch. I prodotti in abbonamento possono applicare limiti d'uso invece di fatturazione puntuale.

Il calcolo base è:

```text
costo = token_input × prezzo_input
      + token_output × prezzo_output
      + strumenti, storage e infrastruttura
```

I prezzi cambiano spesso; inserirli in un foglio di calcolo con data e link è meglio che memorizzarli in un articolo. Confrontate modelli sullo stesso task e sulla stessa qualità, non sul solo prezzo per token. Un modello economico che richiede tre retry può costare più di quello caro al primo tentativo.

## Il costo del contesto si ripete

In una chat lunga, la richiesta nuova è piccola ma il sistema può dover elaborare anche la cronologia. Un documento da 80.000 token non si paga necessariamente una volta: dipende dal caching e dall'architettura del prodotto. Se viene reinviato o riletto, torna nel conto.

Per agenti e MCP si aggiungono definizioni degli strumenti e risultati. Un terminale da migliaia di righe può diventare input al turno successivo. Anthropic ha mostrato un caso in cui spostare filtraggio e orchestrazione in codice ha ridotto il contesto da circa 150.000 a 2.000 token. Non è una percentuale trasferibile a ogni sistema; dimostra che l'interfaccia degli strumenti può dominare il costo.

## Caching: economico solo se il prefisso è stabile

Il prompt caching riusa calcoli su una porzione identica o compatibile del contesto. Per sfruttarlo, istruzioni e documenti stabili vanno prima; dati variabili dopo. Piccole modifiche nella parte iniziale possono invalidare il riuso.

Misurate separatamente letture e scritture di cache. Una cache migliora costo e latenza su richieste ripetute, non su un prompt che cambia integralmente ogni volta.

## Il costo totale di una procedura

Per un flusso professionale aggiungete:

- ricerca e preparazione dei dati;
- revisione umana;
- correzioni e retry;
- integrazione e manutenzione;
- GPU o servizi chiamati;
- errori e incidenti;
- opportunità persa quando il sistema è lento.

Una formula utile è il costo per **esito accettato**, non per chiamata:

```text
(API + infrastruttura + revisione + rework + errori attesi)
---------------------------------------------------------
                 risultati accettati
```

Se il modello dimezza il tempo di una pratica da 40 euro di lavoro umano, discutere di tre millesimi è irrilevante. Se l'app fa un miliardo di classificazioni, quei millesimi diventano il progetto.

## Ottimizzare nell'ordine giusto

1. eliminare chiamate che non cambiano il risultato;
2. ridurre materiale irrilevante e tool output;
3. usare modelli piccoli per routing ed estrazione semplice;
4. inviare al modello potente solo casi difficili;
5. rendere l'output strutturato per evitare retry;
6. usare batch e caching quando il carico lo consente;
7. comprimere solo dopo aver misurato la qualità.

Il routing deve avere una via di escalation. Un classificatore economico che assegna un caso difficile al modello sbagliato può far risparmiare token e perdere il cliente.

## Un foglio di misura minimo

Per ogni task registrate modello, token per categoria, cache, latenza, costo, successo al primo tentativo, minuti di revisione e gravità degli errori. Calcolate mediana e percentile 95: le medie nascondono conversazioni esplose o output anomali.

Fate questa misura prima e dopo ogni ottimizzazione. «Rispondi più breve» può ridurre output e aumentare correzioni; un contesto più piccolo può abbassare costo e perdere un requisito raro.

## Il prezzo cambia; l'economia resta

Il costo unitario dei modelli tende a scendere, ma la domanda cresce e i sistemi diventano più agentici. Un'azione dell'utente può attivare ricerca, decine di tool call e più modelli. Il prezzo della «domanda» non è più una riga di chat: è un grafo di lavoro.

Trattare token, attenzione e rischio come risorse misurabili permette di scegliere. Contare soltanto i token produce sistemi economici che nessuno dovrebbe usare.

Il prezzo dell'elaborazione tende a zero ogni anno. Il prezzo della vostra attenzione no.

## Fonti e approfondimenti

- OpenAI, [API pricing](https://openai.com/api/pricing/), listino corrente.
- Anthropic, [Claude API pricing](https://docs.anthropic.com/en/docs/about-claude/pricing), listino e note sui tool.
- Anthropic, [Prompt caching](https://docs.anthropic.com/en/docs/build-with-claude/prompt-caching), comportamento e misurazione.
- OpenAI, [Prompt caching](https://platform.openai.com/docs/guides/prompt-caching), guida ufficiale.
- Anthropic, [Code execution with MCP](https://www.anthropic.com/engineering/code-execution-with-mcp), caso quantitativo sui tool output.
