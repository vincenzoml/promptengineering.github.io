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

La combinazione buona, in quei casi, è chiedere entrambe le cose separandole: "ragiona pure per esteso, poi chiudi con la risposta in tre righe". Ottenete il ragionamento, che serve al modello, e la sintesi, che serve a voi. Ed è anche il modo migliore per controllarlo: se la sintesi convince e i passaggi no, avete trovato dove sta il problema.
