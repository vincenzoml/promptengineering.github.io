---
title: Come si ottiene una risposta breve
description: "In tre righe" è l'istruzione più sottovalutata che ci sia, e funziona meglio di qualsiasi "sii conciso". Perché i modelli sono prolissi per costruzione, e i quattro modi per farla finita.
date: 2026-05-05
author: vincenzo
tags: [prompt engineering, metodo, LLM]
image: /images/posts/cover-dirgli-di-essere-breve.png
lang: it
---

![Come si ottiene una risposta breve](/images/posts/cover-dirgli-di-essere-breve.png)

Da dove viene la prolissità dei modelli — che non è un caso ma il risultato di una scelta di chi li ha rifiniti; perché "sii conciso" ottiene poco e "in tre righe" molto; e quattro modi di chiedere la brevità che funzionano davvero, compreso quello che nessuno usa.

Una delle lamentele più frequenti, e una delle più facili da risolvere: si fa una domanda semplice e arriva un tema. Introduzione, tre sezioni, conclusione con riepilogo. Voi volevate una riga.

## Perché sono prolissi

Non è un difetto tecnico. È il risultato di come vengono rifiniti.

Nella fase in cui il modello impara quali risposte piacciono, i valutatori umani premiano sistematicamente quelle più complete. È comprensibile: chi valuta una risposta fuori contesto trova più utile quella che copre tutti i casi. Il modello impara la lezione e la generalizza — anche quando la domanda era secca.

C'è anche un effetto pratico: una risposta lunga ha più probabilità di contenere, da qualche parte, quello che cercavate. Sbrodolare è una strategia difensiva, statisticamente vincente per chi viene giudicato a campione.

Il risultato è che la lunghezza è il comportamento predefinito, e va **chiesto esplicitamente** di ridurla. Non lo farà mai spontaneamente.

## Perché "sii conciso" non basta

Perché è un aggettivo, e gli aggettivi sono elastici. "Conciso" per un modello che ha letto milioni di testi accademici significa una cosa diversa da quello che intendete voi.

I numeri invece non sono elastici. "In tre righe", "in cinquanta parole", "una frase", "massimo cinque punti": sono vincoli verificabili, e il modello li rispetta con buona precisione. Non perfetta — conta le parole a occhio, come farebbe una persona — ma la differenza fra "sii breve" e "in cinquanta parole" è la differenza fra una preferenza e un'istruzione.

## I quattro modi che funzionano

**Il numero.** Il più semplice e il più efficace. "Rispondi in tre righe." Se serve una sola cosa: "una frase, niente premesse."

**Il formato.** Chiedere una forma implica una lunghezza. "Rispondi con un elenco puntato, massimo cinque voci." "Compila questa tabella: colonna A, colonna B." Un formato stretto elimina alla radice l'introduzione e il riepilogo, che sono i due punti dove la prosa si gonfia.

**Il divieto esplicito.** Vale la pena dirlo, perché è controintuitivo che serva: "niente introduzione, niente riepilogo finale, niente disclaimer". Sono tre abitudini così radicate che vanno nominate una per una. Chi lavora molto con un modello finisce per tenere questa riga pronta da incollare.

**La regola permanente.** È il modo che quasi nessuno usa, ed è il migliore. Tutti gli strumenti seri consentono di scrivere istruzioni valide per tutte le conversazioni — si chiamano istruzioni personalizzate, o si mettono in un file di progetto. Scriverci dentro "rispondi in modo asciutto, senza premesse né riepiloghi, salvo diversa richiesta" risolve il problema una volta per tutte, invece di ricordarselo ogni giorno.

Due minuti di configurazione contro dieci secondi al giorno per il resto della vita: è il tipo di conto che si fa male, perché il costo ricorrente non si sente.

## L'eccezione

Sulla brevità c'è un caso in cui conviene fare l'opposto, e va detto per non trarre in inganno.

Quando il compito richiede di ragionare — un calcolo articolato, un'analisi con più vincoli, un problema in cui vanno tenute insieme diverse cose — costringere il modello alla brevità **peggiora il risultato**. Scrivere i passaggi è il modo in cui questi sistemi arrivano a conclusioni migliori: tolto lo spazio per farlo, saltano ai risultati, e sbagliano di più.

## Una correzione importante sul «ragionare per esteso»

I modelli recenti possono usare ragionamento interno che non coincide con il testo mostrato. Chiedere una lunga catena di pensiero visibile non è sempre necessario, né garantisce fedeltà: una spiegazione può essere costruita dopo la risposta. Per controllare il lavoro servono evidenze verificabili — calcoli, citazioni, test, assunzioni — non un monologo psicologico.

La formulazione che uso oggi è:

```text
Fai il lavoro con il livello di analisi necessario.
Restituisci la risposta in 5 punti, massimo 120 parole.
Mostra soltanto: ipotesi decisive, calcoli riproducibili, fonti e rischi.
```

Così separo il budget cognitivo dal budget di lettura. La risposta può essere breve senza imporre al sistema una scorciatoia.

## Specificare il contenitore, non l'aggettivo

«Sii conciso» richiede al modello di indovinare quanto. Un contenitore rende la consegna verificabile:

- 80–100 parole per un executive summary;
- 5 bullet, una frase ciascuno;
- una tabella con 4 righe e 3 colonne;
- una decisione, due motivi, un rischio;
- titolo di 60 caratteri e descrizione di 155.

Il limite deve corrispondere al mezzo. Tre righe su un telefono non sono tre righe in Markdown. Parole, caratteri, righe di tabella o numero di sezioni sono misure più stabili.

Un'altra tecnica è assegnare una priorità editoriale:

```text
Se devi tagliare, conserva nell'ordine: decisione, eccezioni, numeri,
azioni. Elimina nell'ordine: introduzioni, ripetizioni, contesto già noto,
aggettivi.
```

Senza priorità, il modello può rispettare la lunghezza eliminando proprio il caveat che rende la risposta corretta.

## Progressive disclosure

Una risposta breve non deve contenere tutto. Può essere il primo strato di un oggetto navigabile:

1. una sintesi che sta sullo schermo;
2. dettagli per ciascun punto;
3. appendice con fonti, dati e metodo.

È il formato naturale per documenti decisionali e articoli online. Il lettore interrompe dopo il primo livello senza perdere la conclusione; chi deve verificare può scendere.

Un prompt corrispondente:

```text
Apri con una risposta autosufficiente di 100 parole.
Segue una sezione per ciascuna ipotesi, leggibile indipendentemente.
Chiudi con metodo e fonti. Non anticipare nell'introduzione ciò che il
lettore può trovare sotto.
```

## Brevità nei sistemi agentici

Per un agente di coding la verbosità non occupa solo lo schermo. Aggiornamenti, log e risultati degli strumenti possono restare nel contesto e venire riletti a ogni turno. Qui serve una politica: silenzio sulle azioni ordinarie, interruzioni per rischio o decisioni, output dei comandi filtrati vicino alla sorgente.

La sintesi finale deve comunque essere operativa: file cambiati, verifiche, questioni residue. «Fatto» è breve ma non consente controllo.

## Un piccolo protocollo di compressione

Quando una risposta è troppo lunga, non chiedete subito di «accorciarla». Fate tre passaggi:

1. estrarre le affermazioni indispensabili;
2. ordinare per decisione del lettore;
3. comprimere eliminando duplicazioni, non prove.

Poi controllate che numeri, negazioni ed eccezioni siano sopravvissuti. Sono gli elementi che più facilmente spariscono in una sintesi e che più spesso cambiano il significato.

La brevità riuscita non dice meno del necessario. Fa pagare a ogni frase l'affitto dello spazio che occupa.

## Ragionamento lungo, consegna corta

La combinazione buona, in quei casi, è chiedere entrambe le cose separandole: "ragiona pure per esteso, poi chiudi con la risposta in tre righe". Ottenete il ragionamento, che serve al modello, e la sintesi, che serve a voi. Ed è anche il modo migliore per controllarlo: se la sintesi convince e i passaggi no, avete trovato dove sta il problema.

## Fonti e approfondimenti

- Anthropic, [Effective context engineering for AI agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents), sul rapporto segnale/rumore nel contesto.
- Anthropic, [Code execution with MCP](https://www.anthropic.com/engineering/code-execution-with-mcp), sull'effetto degli output degli strumenti.
- OpenAI, [Reasoning best practices](https://platform.openai.com/docs/guides/reasoning-best-practices), sul modo di istruire modelli di ragionamento.
- Liu et al., [Lost in the Middle](https://arxiv.org/abs/2307.03172), sull'uso dell'informazione nei contesti lunghi.
