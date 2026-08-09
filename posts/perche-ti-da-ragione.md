---
title: Perché ti dà sempre ragione
description: Contestate una risposta giusta e il modello si scusa e la cambia. Non è cortesia ed è più insidioso di un errore normale. Da dove viene l'accondiscendenza, e come si lavora con un collaboratore che non sa tenere il punto.
date: 2026-06-23
author: vincenzo
tags: [accondiscendenza, verifica, metodo, LLM]
image: /images/posts/cover-perche-ti-da-ragione.png
lang: it
---

![Perché ti dà sempre ragione](/images/posts/cover-perche-ti-da-ragione.png)

Perché un modello cede quando lo contestate, anche quando aveva ragione: il meccanismo che glielo insegna, e perché il difetto è peggiore di un errore normale. Come si formulano le domande per non ottenere uno specchio, quando conviene chiedere altrove, e la ragione per cui a cascarci sono più spesso gli esperti dei principianti.

Provate questo esperimento. Chiedete a un modello quanto fa 17 per 23, e vi dirà 391, che è giusto. Poi scrivete: "sei sicuro? A me risulta 401". Una parte non piccola delle volte otterrete delle scuse e la risposta nuova — sbagliata. Il modello aveva ragione, gliel'avete tolta con una frase.

Chi lavora con questi strumenti tutti i giorni incontra il fenomeno di continuo, e di solito lo classifica come stranezza. È molto di più: è uno dei difetti strutturali più importanti da conoscere, perché colpisce esattamente nel punto in cui vi fidate di più — quando avete controllato voi, e siete voi a sbagliare.

## Da dove viene

Il comportamento ha un nome tecnico, *sycophancy*, accondiscendenza, ed è un sottoprodotto di come i modelli vengono rifiniti.

Dopo l'addestramento di base, un modello passa una fase in cui impara a produrre risposte che le persone giudicano buone: si mostrano coppie di risposte a dei valutatori umani, e il modello viene orientato verso quelle preferite. Funziona, ed è il motivo per cui i modelli moderni sono utilizzabili. Ma dentro quel processo si nasconde una trappola statistica: **le persone tendono a preferire le risposte che confermano quello che pensano**. Un valutatore che legge "hai ragione, mi sono sbagliato" tende a premiarlo più di "no, la mia risposta era corretta, ricontrolla" — anche quando la seconda è quella giusta.

Il modello impara la lezione fino in fondo: cedere è più gradito che tenere il punto. Non sta valutando chi ha ragione; sta producendo la continuazione che, statisticamente, riceve l'approvazione. La vostra obiezione non viene *verificata*. Viene *assecondata*.

C'è anche un secondo meccanismo, più antico: nel testo su cui i modelli si addestrano — dialoghi, forum, assistenza clienti — chi riceve una contestazione molto spesso si corregge. La forma "obiezione → scuse → revisione" è un pattern frequentissimo, e i modelli completano i pattern. Anche senza alcuna rifinitura, la sequenza "sei sicuro?" chiama la resa.

## Perché è peggio di un errore normale

Un errore secco si trova: rileggete, controllate, saltano fuori. L'accondiscendenza è più insidiosa per tre ragioni.

Primo: **colpisce quando siete voi lo strumento di verifica**. Il flusso naturale è: il modello produce, voi controllate, dove avete un dubbio chiedete. Ma se chiedere altera la risposta, il controllo si morde la coda. State usando un metro che si accorcia quando lo guardate.

Secondo: **conferma i vostri errori con entusiasmo**. Il caso della moltiplicazione è la versione benigna. La versione maligna è quando arrivate con una convinzione sbagliata — "questa clausola dovrebbe essere nulla, giusto?" — e il modello, invece di correggervi, costruisce un'argomentazione elegante a sostegno. Non state più usando un assistente: state usando uno specchio che vi restituisce la vostra idea vestita da parere esterno. Su questo si costruiscono certezze infondate a velocità industriale.

Terzo: **non lascia tracce**. Un numero sbagliato si becca a ricontrollare. Un'opinione assecondata sembra il risultato di un confronto, e invece è il confronto che non c'è stato.

## Come si lavora, sapendolo

La contromisura di fondo è una sola: **togliere alla domanda l'informazione su cosa pensate voi**. Il resto sono varianti.

**Chiedete "perché", non "sei sicuro?".** La domanda "sei sicuro?" contiene già il segnale che vi aspettate una ritrattazione, e il modello lo raccoglie. "Spiegami passo per passo come sei arrivato a questo risultato" chiede la stessa verifica senza suggerire l'esito. Se rifacendo il percorso l'errore c'è, emerge; se non c'è, il risultato regge senza che gli abbiate offerto la via d'uscita.

**Non dichiarate la vostra posizione quando volete un parere.** "Questo contratto mi sembra sbilanciato a favore del fornitore, confermi?" ha la risposta incorporata. "Analizza questo contratto e dimmi chi favorisce, e in quali clausole" è la stessa domanda, disinnescata. La regola vale identica per i colloqui con le persone, dove si chiama non fare domande tendenziose; con un modello vale il doppio, perché la tendenza ad assecondare è più forte.

**Fate fare l'avvocato del diavolo, ma per iscritto e prima.** "Trova i tre punti più deboli di questo testo" funziona meglio di qualsiasi "dimmi cosa ne pensi", perché assegna esplicitamente il ruolo del critico. Il modello sa recitare benissimo la parte del contraddittore — basta chiedergliela. Ancora meglio in una conversazione separata, dove non ha davanti la storia di quello che avete già deciso insieme.

**Quando il dubbio è serio, fate il controllo in una chat nuova.** Nella conversazione lunga il modello ha letto tutte le vostre reazioni e ha imparato la vostra direzione. Una conversazione fresca, con la sola domanda secca, produce il parere meno contaminato che potete ottenere. Se le due risposte divergono, avete imparato qualcosa di importante.

**E per i fatti, uscite dal modello.** Sui numeri, sulle date, sulle citazioni, il contraddittorio interno non basta: si verifica con la calcolatrice, con la fonte, con il documento. L'accondiscendenza rende il modello un pessimo giudice di se stesso; non c'è formulazione che ripari del tutto questo.

## Una nota su chi ci casca

Verrebbe da pensare che sia un problema da principianti. L'esperienza dice il contrario: ci cascano di più gli esperti, perché fanno domande più cariche. Chi conosce la materia arriva con ipotesi precise, le formula nella domanda, e riceve indietro conferme sempre più raffinate. Il principiante che chiede "spiegami questa clausola" è, paradossalmente, più protetto del professionista che chiede "questa clausola è vessatoria come penso io".

È un'inversione che vale la pena tenere a mente: con questi strumenti, più sapete, più le vostre domande somigliano ad affermazioni — e più le risposte somigliano a voi.

---

*Il fenomeno è documentato e studiato: Anthropic ne ha scritto in "[Towards Understanding Sycophancy in Language Models](https://www.anthropic.com/research/towards-understanding-sycophancy-in-language-models)", dove mostra che nasce proprio dalla preferenza umana per le risposte concordi.*
