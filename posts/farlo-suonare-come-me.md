---
title: Come si insegna a un modello la propria voce
description: Descrivere il proprio stile a parole non funziona quasi mai. Funziona dargli tre cose che avete scritto — e sapere quali tre. Il procedimento, e il punto in cui conviene fermarsi.
date: 2026-04-14
author: vincenzo
tags: [voce, scrittura, prompt engineering]
image: /images/posts/cover-farlo-suonare-come-me.png
lang: it
---

![Come si insegna a un modello la propria voce](/images/posts/cover-farlo-suonare-come-me.png)

Perché "scrivi con il mio stile" non basta e cosa metterci al posto; come si scelgono i tre testi da dargli in pasto; come si costruisce una scheda di voce riutilizzabile; e la ragione per cui, superato un certo punto, conviene smettere.

Chi scrive per mestiere prova prima o poi a farsi imitare, e la prima volta va male. Il modello produce un testo corretto che non somiglia a niente di vostro. Chiedere "scrivi con il mio stile" non funziona per un motivo semplice: il modello non sa qual è il vostro stile, e voi — provate — non sapete descriverlo.

## Perché la descrizione fallisce

Provate ad articolare come scrivete. Vengono fuori cose tipo "chiaro", "diretto", "non troppo formale". Sono le stesse tre parole che direbbe chiunque, e infatti producono la prosa di chiunque.

Lo stile vero sta in dettagli che non sappiamo di avere: quanto sono lunghe le nostre frasi, se apriamo con la conclusione o ci arriviamo, se usiamo i due punti, se facciamo domande retoriche, quanto spesso ci concediamo un aggettivo, se citiamo casi o restiamo sull'astratto. Nessuno ha in testa questo elenco. Ma il modello lo estrae da solo, se gli si danno esempi invece di aggettivi.

## Quali testi dare

Non i più belli: **i più tipici**. Un testo particolarmente riuscito è spesso un'eccezione, e imitandolo si ottiene una caricatura.

Tre testi bastano, e la scelta conta più della quantità. Prendetene tre dello stesso genere di quello che volete produrre — se vi serve una lettera a un cliente, date tre lettere a clienti, non un articolo e due relazioni. Il genere pesa sullo stile più della persona: la stessa mano scrive in modo diverso una diffida e una mail interna.

E dateli interi. Un frammento perde la struttura, che è metà della voce.

## Il procedimento

Il giro che funziona è in tre mosse.

**Prima, fatevi descrivere.** "Leggi questi tre testi. Descrivi in dieci punti precisi come sono scritti: lunghezza delle frasi, struttura dei paragrafi, registro, punteggiatura, cosa evitano, come aprono e come chiudono." La descrizione che ne esce è quasi sempre più acuta di quella che avreste dato voi, ed è già utile a prescindere: si scopre qualcosa sul proprio modo di scrivere.

**Seconda, correggete.** Il modello noterà cose vere e cose accidentali. "Il punto sette è casuale, era un vezzo di quel testo. Il punto tre invece è centrale: tienilo." Qui state costruendo, di fatto, la vostra scheda di voce.

**Terza, salvatela.** Quei dieci punti, corretti, diventano un testo riutilizzabile: nelle istruzioni personalizzate, in un file di progetto, o semplicemente in una nota da incollare. Ed è a questo punto che il lavoro comincia a rendere, perché non lo rifate più.

## Dove ci si ferma

Dopo due o tre giri, il modello scrive qualcosa che vi somiglia abbastanza da essere una prima stesura utile. Non abbastanza da pubblicare senza toccare.

La distanza che resta, secondo me, non è tecnica. Un testo suona vostro anche perché contiene le vostre scelte — quello che decidete di non dire, il caso che vi viene in mente, il punto in cui vi contraddite. Nessuna quantità di esempi produce quello, perché non è nello stile: è nel fatto di avere qualcosa da dire.

## Lo stile non è una lista di aggettivi

«Autorevole ma accessibile, brillante ma non informale» descrive quasi ogni brief editoriale. Non dice dove aprire una frase, quanta informazione mettere in un paragrafo, come usare esempi o quando ammettere incertezza.

Una voce riconoscibile è un fascio di decisioni osservabili:

- rapporto fra esperienza personale e prove esterne;
- lunghezza e variazione delle frasi;
- lessico tecnico e modo di definirlo;
- frequenza di metafore, domande e parentesi;
- trattamento del dissenso e dell'incertezza;
- struttura dell'apertura e della chiusura;
- cose che l'autore rifiuta sistematicamente di fare.

Gli esempi permettono al modello di inferire queste regolarità. Ma vanno scelti per coprire il repertorio: un pezzo analitico, uno narrativo e uno operativo dicono più di tre articoli quasi identici.

## Costruire una scheda di voce verificabile

Chiedo prima un'analisi, senza generazione:

```text
Confronta questi tre testi. Trova solo caratteristiche presenti in almeno
due esempi e cita i passaggi che le mostrano. Separa struttura, sintassi,
lessico, uso delle fonti e relazione con il lettore. Elenca anche cinque
abitudini da non imitare perché dipendono dall'argomento.
```

Poi trasformo l'analisi in una scheda corta. Ogni regola deve poter essere controllata: «apri con un episodio o un conflitto concreto» è migliore di «sii coinvolgente»; «nessuna citazione senza link primario» è migliore di «sii rigoroso».

Infine tengo esempi positivi e negativi. Il negativo evita caricature: se il modello ha scambiato la mia ironia occasionale per una battuta ogni due paragrafi, mostro il difetto e lo nomino.

## Il test cieco

La somiglianza percepita dall'autore non basta. Preparate tre brevi testi sullo stesso tema: originale umano, modello con prompt generico, modello con scheda ed esempi. Fateli valutare senza etichetta da persone che conoscono la vostra scrittura.

Non chiedete solo «qual è il suo?». Chiedete quali segnali hanno usato, dove la voce si rompe, quale passaggio sembra generico e quale introduce una posizione reale. L'errore di attribuzione è informativo: può rivelare che il vostro stile pubblico è meno distinto di quanto pensavate.

Uno studio EMNLP 2025 su oltre 40.000 generazioni e 400 autori ha trovato che i modelli possono avvicinarsi a stili strutturati, mentre faticano con registri informali e sfumati di blog e forum. Il risultato mette in guardia dalle demo scelte a mano: imitare superficie e formato non equivale a riprodurre una voce.

## Dalla voce alla responsabilità editoriale

Un modello può apprendere che uso frasi brevi. Non sa quale episodio della mia vita sia appropriato, quale collega possa essere nominato, quale giudizio sia disposto a difendere pubblicamente. Queste sono scelte, non stile.

Per questo il flusso migliore assegna all'AI lavori distinti:

1. interrogare appunti e fonti;
2. proporre strutture alternative;
3. preparare una prima stesura vincolata alla scheda;
4. segnalare dove mancano esperienza, prova o presa di posizione;
5. lasciare all'autore quei punti;
6. fare un controllo finale contro esempi e divieti.

I passaggi umani non sono il residuo romantico. Sono il luogo in cui entra informazione che non era nel modello.

## Aggiornare la voce senza congelarla

Una scheda ricavata dai testi passati può trasformare un'abitudine in una prigione. Va versionata. Ogni pochi mesi aggiungete lavori riusciti, eliminate regole che producono manierismo e annotate nuove scelte. Conservate la provenienza degli esempi: un testo fortemente editato da altri non è un campione neutro.

Per lavori delicati, dichiarate l'uso dell'AI secondo contesto e policy. L'obiettivo non è costruire un falso Vincenzo automatico. È usare la macchina per togliere attrito senza cedere firma, fatti e giudizio.

## Il trenta per cento che vale

Il che ridimensiona l'obiettivo in modo utile. Non serve un modello che scriva al posto vostro. Serve un modello che vi porti al settanta per cento in due minuti, lasciandovi il trenta che vale — che è poi il pezzo per cui vi pagano.

## Fonti e approfondimenti

- Wang et al., [Catch Me If You Can? Not Yet: LLMs Still Struggle to Imitate the Implicit Writing Styles of Everyday Authors](https://aclanthology.org/2025.findings-emnlp.532/), Findings of EMNLP 2025.
- Baumler et al., [Can You Make It Sound Like You? Post-Editing LLM-Generated Text for Personal Style](https://aclanthology.org/2026.acl-long.2030/), ACL 2026.
- OpenAI, [Prompt engineering](https://platform.openai.com/docs/guides/prompt-engineering), su esempi e istruzioni.
- Madaan et al., [Self-Refine](https://arxiv.org/abs/2303.17651), su feedback e revisione iterativa.
