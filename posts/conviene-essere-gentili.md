---
title: Conviene essere gentili con un modello?
description: La domanda sembra oziosa e non lo è. Il modello non si offende, ma la cortesia cambia comunque quello che ottenete — per una ragione che non ha niente a che fare con i sentimenti.
date: 2026-06-02
author: vincenzo
tags: [prompt engineering, metodo, LLM]
image: /images/posts/cover-conviene-essere-gentili.png
lang: it
---

![Conviene essere gentili con un modello?](/images/posts/cover-conviene-essere-gentili.png)

Se "per favore" serva a qualcosa, perché la risposta è sì per un motivo che non c'entra con la buona educazione, e cosa succede davvero quando si scrive in modo brusco. Più una nota su cosa si consuma, dato che qualcuno l'ha misurato.

La domanda arriva quasi sempre a metà di un corso, e chi la fa si scusa prima di farla. "Lo so che è stupida, ma: conviene dire per favore?"

Non è stupida. La risposta però non sta dove uno se la aspetta.

## Il modello non si offende

Cominciamo dal punto che si può liquidare in fretta. Un modello linguistico non prova niente. Non c'è nessuno lì dentro a cui la maleducazione dispiaccia, e nessuna memoria in cui il torto resti. Se lo insultate e poi gli chiedete un favore, non c'è rancore che gli faccia rispondere peggio.

Chi dice "sono gentile per abitudine" fa benissimo, e chi dice "risparmio i convenevoli" pure. Sul piano morale non sta succedendo niente.

## Però la cortesia cambia il testo

Qui viene la parte interessante. Le richieste scritte con cortesia tendono a essere **anche** richieste scritte meglio, e il modello risponde al testo.

Confrontate:

```
Riassumi
```
con
```
Potresti riassumermi questo verbale in dieci righe,
tenendo i nomi delle parti e le date?
```

La seconda è più educata, ma soprattutto è più lunga, più specifica, e contiene tre informazioni che nella prima non c'erano. Il modello non ha percepito il garbo: ha ricevuto istruzioni.

C'è anche un secondo effetto, meno ovvio. Nei testi su cui questi sistemi si sono formati, il registro cortese si accompagna a un certo tipo di contenuto — risposte curate, complete, professionali — mentre il registro sbrigativo compare in scambi rapidi e superficiali. Scrivendo in un registro, il modello tende a continuare in quello. Non perché reagisca al tono, ma perché il tono è un pezzo del contesto, e il contesto orienta tutto.

Una collega mi ha raccontato una prova involontaria: aveva scritto una richiesta di fretta, in maiuscolo, con tre punti esclamativi, e aveva ricevuto una risposta breve e sbrigativa. Riscritta con calma, la stessa domanda aveva prodotto un'analisi di due pagine. Il modello aveva raccolto il segnale "questo scambio è veloce" e si era regolato.

## Quello che non serve

Dette queste cose, c'è tutta una categoria di formule che circolano e che non fanno niente.

Promettere mance non ha alcun effetto misurabile. Minacciare conseguenze nemmeno. Le implorazioni drammatiche del tipo "è importantissimo per la mia carriera" appartengono al folclore dei primi modelli, e sui sistemi attuali sono rumore: occupano spazio nel contesto e non spostano niente. Se avete visto girare una lista di "frasi magiche", trattatela come tale.

Vale invece dire il perché reale, quando c'è: "serve per un cliente che non conosce la materia" cambia la risposta, perché è un'informazione sul destinatario, non un tentativo di persuasione.

## E i costi?

C'è un risvolto che è stato notato pubblicamente e fa sorridere. "Per favore" e "grazie" sono parole, le parole sono frammenti da elaborare, e i frammenti costano corrente. Con centinaia di milioni di conversazioni al giorno, quei convenevoli diventano una voce di spesa reale per chi gestisce i centri di calcolo — la questione è finita sui giornali, con stime che vanno dai milioni di dollari in su.

Per un singolo utente, però, è irrilevante: parliamo di frazioni infinitesime di centesimo. Se qualcuno vi dice di smettere di ringraziare per risparmiare, sta ottimizzando la cosa sbagliata.

## Quindi

Siate cortesi se vi viene naturale, che non costa niente e produce richieste migliori. Siate telegrafici se preferite, ma allora siate telegrafici *e precisi*: la brevità che funziona è quella che toglie le cerimonie e tiene le istruzioni, non quella che toglie tutto.

Il vero motivo per cui vale la pena scrivere bene a una macchina è un altro, e me l'ha fatto notare un avvocato dopo due giorni di corso: aveva cominciato a scrivere istruzioni più chiare ai modelli, e si era accorto di averle cominciate a scrivere più chiare anche ai collaboratori. Il modello, in quel caso, era stato un ottimo maestro di sintesi — perché è l'unico interlocutore che non colma mai i vuoti da solo.
