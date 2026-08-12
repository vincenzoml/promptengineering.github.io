---
title: Fatevi trovare i difetti, non i complimenti
description: La richiesta più utile che si possa fare a un modello è di demolire quello che ha appena scritto. Funziona bene, per una ragione precisa — e ci sono tre modi di chiederlo, uno molto migliore degli altri.
date: 2026-03-24
author: vincenzo
tags: [revisione, metodo, verifica]
image: /images/posts/cover-chiedergli-di-criticarsi.png
lang: it
---

![Fatevi trovare i difetti, non i complimenti](/images/posts/cover-chiedergli-di-criticarsi.png)

Perché un modello è un critico migliore di quanto sia autore, come si formula la richiesta perché produca obiezioni vere invece di finta modestia, i tre modi di farlo in ordine di efficacia, e il limite che questa tecnica non supera.

Fra tutte le cose che si possono chiedere a un modello, quella che rende di più è anche una delle meno usate: **trova i punti deboli di questo testo**.

Funziona meglio di quanto ci si aspetti, e il motivo è strutturale.

## Perché critica meglio di quanto scriva

Scrivere richiede di scegliere una direzione fra molte plausibili, e la scelta del modello è quella statisticamente media. Criticare richiede di confrontare un testo con dei criteri — e i criteri, il modello, li conosce benissimo: ha letto migliaia di revisioni, obiezioni, pareri contrari, relazioni di minoranza.

C'è anche una ragione più prosaica. Quando scrive, deve produrre tutto; quando critica, il testo c'è già e lui deve solo esaminarlo. È un compito più circoscritto, e nei compiti circoscritti questi sistemi sono molto più affidabili.

L'esperienza pratica lo conferma: le obiezioni che tira fuori sono spesso banali, ma su dieci ce ne sono due che avreste preferito trovare voi.

## Come chiederlo

**Il modo peggiore**: "che ne pensi?" Ottenete un complimento seguito da due suggerimenti generici. È la domanda che invita all'accondiscendenza, ed è precisamente il difetto che questi sistemi hanno di serie.

**Meglio**: "trova i tre punti più deboli di questo testo." Il numero obbliga a produrne tre anche se il testo gli sembra buono, e l'obbligo fa emergere cose vere. Senza il numero, se ne cava uno di cortesia.

**Meglio ancora**: assegnare un ruolo con un interesse contrario. "Sei l'avvocato della controparte. Leggi questa lettera e dimmi dove attaccheresti." "Sei un cliente diffidente: quali domande faresti dopo aver letto questa proposta?" Il ruolo dà al modello un criterio con cui giudicare, e i criteri producono critiche specifiche invece che generiche.

**Il modo migliore**, e quello che quasi nessuno usa: **farlo in una conversazione separata**.

## Perché la conversazione nuova cambia tutto

Nella conversazione in cui il testo è nato, il modello ha davanti tutta la storia: le vostre reazioni, i pezzi che avete scartato, le direzioni che avete approvato. Ha imparato cosa vi piace, e la sua critica ne risente — perché tutto quello che sta nel contesto orienta quello che scrive.

Aprendo una conversazione pulita e incollando solo il testo, ottenete un giudizio non contaminato. È la stessa ragione per cui un collega che non ha seguito il progetto vede in dieci minuti il problema che voi non vedevate da tre settimane.

Chi lavora molto con questi strumenti finisce per tenere due conversazioni in parallelo: una in cui costruisce, una in cui fa a pezzi. E funziona meglio della stessa che fa entrambe le cose.

## Il limite

Un modello non sa se una cosa è vera. Vi dirà che un'argomentazione è debole, che una struttura non regge, che una frase è ambigua, che manca un passaggio logico. Non vi dirà che il numero è sbagliato, che quella sentenza non esiste, che quel cliente si offenderà.

La critica che ottenete è **formale**, e va presa per quello che è: una revisione di struttura e di tenuta, non un controllo dei fatti né una valutazione delle conseguenze. Chi confonde le due cose finisce per fidarsi di un testo ben costruito e sbagliato.

## Perché «criticati» da solo serve poco

Una critica senza criterio tende a diventare un genere letterario. Il modello elenca vaghezza, ripetizioni e bisogno di esempi; poi riscrive il testo con la stessa tesi e qualche connettivo in più. Ha eseguito la forma della revisione, non ha messo davvero alla prova il lavoro.

Servono tre elementi: un punto di vista avversario, una griglia osservabile e una conseguenza. Per una proposta commerciale, per esempio:

```text
Agisci come il responsabile acquisti che vuole respingere questa proposta.
Non riscriverla. Trova fino a sette ragioni concrete di rifiuto.
Per ciascuna cita il passaggio, indica quale prova manca, assegna gravità
e spiega quale modifica minima potrebbe cambiare la decisione.
Non premiare tono o scorrevolezza se la tesi non è dimostrata.
```

Per un articolo scientifico cambiano criteri e avversario: validità interna, selezione del campione, baseline, leakage, potere statistico, distinzione fra risultato ed estrapolazione. Per un contratto occorrono giurisdizione, allocazione del rischio, definizioni e casi limite. Il prompt di critica eredita la competenza del modello e la qualità della griglia che gli diamo.

## Tre revisioni, tre errori diversi

Conviene separare controlli che altrimenti si coprono a vicenda.

**Revisione argomentativa.** La conclusione segue dalle premesse? Ci sono alternative escluse senza prova? Una correlazione viene trattata come causa? Qui il modello è utile anche senza accesso al web, perché lavora sulla struttura presente.

**Revisione fattuale.** Numeri, nomi, date e citazioni sono sostenuti da fonti? Qui serve accesso ai documenti originali. Il modello deve produrre una tabella affermazione–fonte–passaggio, non una rassicurazione.

**Revisione editoriale.** Il destinatario capisce, l'ordine è progressivo, i termini sono definiti, la densità è adeguata? Va fatta dopo le prime due. Lucidare una premessa falsa la rende soltanto più pericolosa.

## Il metodo a due modelli non è indipendenza

Far criticare il testo da un secondo modello è utile, ma non crea automaticamente due osservatori indipendenti. I sistemi possono condividere dati, convenzioni e punti ciechi; un errore plausibile viene spesso accettato da entrambi. La diversità aiuta di più quando cambia il metodo: un modello legge la prosa, un programma ricontrolla i calcoli, una ricerca trova le fonti, una persona competente valuta le conseguenze.

Per le decisioni importanti costruisco una «scala di prova»:

1. il testo dichiara l'affermazione;
2. la fonte primaria la sostiene;
3. un calcolo o test la riproduce, se possibile;
4. un revisore comprende limiti e alternative;
5. chi firma accetta il rischio residuo.

L'AI accelera i passaggi, non li fonde.

## Che cosa dice la ricerca sull'autocorrezione

*Self-Refine* ha mostrato miglioramenti medi su più compiti iterando feedback e revisione senza addestramento aggiuntivo. *Reflexion* ha studiato agenti che conservano feedback verbale fra tentativi. Sono risultati importanti: l'output iniziale non è il limite del modello.

Non dimostrano che ogni autocritica converga verso la verità. Studi successivi hanno osservato casi in cui il feedback del modello premia segnali sbagliati o la revisione degrada risposte inizialmente corrette. Se il giudice è lo stesso sistema che ha generato la soluzione, il ciclo può ottimizzare persuasività invece di accuratezza.

La difesa è introdurre evidenza esterna e criteri prima della risposta. «Controlla se hai ragione» è debole. «Ricalcola con questo interprete, verifica ogni DOI sul sito dell'editore e marca ciò che non trovi» è un protocollo.

## Un ciclo di revisione riutilizzabile

Per testi professionali uso quattro passaggi brevi:

1. **Diagnosi:** nessuna riscrittura; difetti ordinati per rischio.
2. **Piano:** per ogni difetto, prova o decisione necessaria.
3. **Correzione:** cambiare solo i passaggi coinvolti, conservando una traccia.
4. **Controllo ostile:** cercare nuovi errori introdotti dalla revisione.

Alla fine chiedo una tabella con «risolto», «attenuato», «aperto». Le questioni aperte non devono sparire dentro una prosa più sicura.

Il vantaggio principale dell'autocritica non è ottenere un verdetto. È produrre una mappa dei punti in cui vale la pena spendere verifica umana.

## Trenta secondi, e a volte una figuraccia in meno

Con quel limite in mente, resta la richiesta con il miglior rapporto fra costo e resa che io conosca. Trenta secondi, e a volte vi risparmia una figuraccia.

## Fonti e approfondimenti

- Madaan et al., [Self-Refine](https://arxiv.org/abs/2303.17651), 2023.
- Shinn et al., [Reflexion: Language Agents with Verbal Reinforcement Learning](https://arxiv.org/abs/2303.11366), 2023.
- Pan et al., [Spontaneous Reward Hacking in Iterative Self-Refinement](https://arxiv.org/abs/2407.04549), sui rischi dei segnali di ricompensa prodotti dal modello.
- Anthropic, [Towards Understanding Sycophancy in Language Models](https://www.anthropic.com/research/towards-understanding-sycophancy-in-language-models), sul bias verso risposte gradite all'utente.
