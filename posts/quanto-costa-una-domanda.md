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

L'unità di misura non è la parola: è il **token**, un frammento. I modelli spezzano il testo in pezzi che a volte sono parole intere, più spesso sillabe o gruppi di lettere. "Intelligenza" può diventare tre o quattro token. I numeri si spezzano in modo capriccioso, la punteggiatura conta, gli spazi anche.

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

Il prezzo dell'elaborazione tende a zero ogni anno. Il prezzo della vostra attenzione no.
