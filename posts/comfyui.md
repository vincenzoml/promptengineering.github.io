---
title: ComfyUI, ovvero smettere di tirare a indovinare
description: I generatori di immagini con la casella di testo nascondono tutto quello che conta. ComfyUI mostra i passaggi uno per uno — ed è per questo che sembra difficile, e per questo che poi non si torna indietro.
date: 2026-07-14
author: vincenzo
tags: [ComfyUI, immagini, modelli aperti, laboratorio]
image: /images/posts/cover-comfyui.png
lang: it
---

![ComfyUI](/images/posts/cover-comfyui.png)

Per capire come funziona davvero la generazione di immagini bisogna vedere l'impianto, e ComfyUI è lo strumento che lo mostra tutto. Questo articolo racconta cosa c'è dietro la casella di testo, il momento preciso in cui si smette di tirare a indovinare, e perché quella trasparenza costi così cara in manutenzione — una domanda che porta dritta al motivo per cui, alla fine, ho cominciato a costruire [Anymatix](https://www.anymatix.com/).

Ma partiamo dal fastidio che conoscono tutti.

Chi ha usato Midjourney o la generazione di immagini dentro ChatGPT conosce la sensazione: scrivi una frase, esce qualcosa, spesso è bello, ogni tanto è esattamente quello che serviva. E quando non lo è, non si sa cosa toccare. Si riscrive la frase in un altro modo, si aggiunge "fotorealistico", si toglie "fotorealistico", si spera. Dopo dieci tentativi si ha una cartella di immagini quasi giuste e nessuna idea del perché la undicesima dovrebbe andare meglio.

ComfyUI parte dall'altro capo. Al posto della casella di testo c'è una tela con dei riquadri collegati da fili, e ogni riquadro è un passaggio del procedimento. La prima impressione è quella di un impianto elettrico visto da dietro il quadro. La seconda impressione, che arriva dopo un'ora, è la scoperta che i passaggi erano sempre quelli, in ogni strumento che avete usato — solo che ve li avevano coperti.

## Cosa c'era sotto la casella di testo

Generare un'immagine con un modello a diffusione significa, in sostanza, quattro cose, e vale la pena conoscerle anche se non installerete mai niente, perché spiegano i comportamenti strani di *tutti* i generatori.

Si parte da **rumore**: un'immagine di puntini casuali, il nevischio dei vecchi televisori. Il testo che avete scritto viene convertito in numeri da un componente apposito, che ha i suoi gusti e i suoi limiti — è qui che "un gatto senza cappello" produce spesso un gatto col cappello: la negazione è una faccenda linguistica sottile, e questo componente è la parte meno raffinata della catena. Poi il modello, per un numero fissato di passaggi, **toglie rumore un po' alla volta**, orientandosi con quei numeri: a ogni passo l'immagine è meno nevischio e più gatto. Alla fine un decodificatore trasforma il risultato in pixel veri.

Nell'interfaccia con la casella di testo tutto questo esiste identico, ma le scelte le ha fatte qualcun altro: quale modello, quanti passaggi, quanto deve pesare il vostro testo rispetto alla libertà del modello, da quale rumore si parte. In ComfyUI ogni scelta è un riquadro che potete guardare e cambiare. Non è questione di potenza — è che quando il risultato non torna, finalmente sapete *dove* mettere le mani, invece di riscrivere la frase e sperare.

## Il momento in cui scatta

Per me è scattato con il **seed**, il numero da cui nasce il rumore iniziale.

Con un'interfaccia normale, la stessa richiesta due volte dà due immagini diverse, e non sapete perché. Con il seed fissato, la stessa richiesta dà **la stessa immagine, identica, per sempre**. Sembra un dettaglio da pignoli ed è la chiave di tutto: da lì in poi cambiate una cosa sola — un passaggio in più, una parola diversa, un peso ritoccato — e vedete esattamente cosa ha prodotto quel cambiamento, perché tutto il resto è inchiodato.

È la differenza fra provare ed esperimentare. Provando si accumulano impressioni vaghe ("mi pare che con più passaggi venga meglio"); sperimentando si impara qualcosa che resta vero anche domani. Ed è lo stesso principio che regge il lavoro sul testo: se cambiate cinque cose in un prompt e il risultato migliora, non sapete quale delle cinque ha funzionato, e quel miglioramento non è vostro — è capitato. Una alla volta è più lento il primo giorno e più veloce tutti gli altri.

C'è un piacere particolare, quasi fisico, nel primo pomeriggio con il seed fissato. Si smette di essere spettatori di una lotteria e si comincia a girare le manopole di una macchina. La macchina era sempre stata lì.

## Come si comincia sul serio

Il consiglio che darei a me stesso di due anni fa: non costruire niente da zero, e non scaricare il flusso più spettacolare che trovi.

Si installa ComfyUI, si apre il flusso di esempio che arriva già montato, e **lo si fa girare così com'è**, senza capirlo tutto. Poi si cambia una cosa. Il numero dei passaggi: cosa succede con quattro? Con cinquanta? Il peso del testo: e se lo abbasso? Ogni manopola girata con il seed fermo è una piccola lezione privata. In una settimana di mezze ore si è capito il novanta per cento di quello che servirà.

La comunità pubblica flussi già fatti per quasi tutto — ritratti, correzione di dettagli, ingrandimento, sostituzione di sfondi — e sono file che si trascinano dentro la finestra. Studiarne uno fatto bene insegna più di qualsiasi guida, perché un flusso è un ragionamento congelato: qualcuno ha messo quei passaggi in quell'ordine per un motivo, e i motivi si vedono, riquadro per riquadro. È il vantaggio strutturale della trasparenza: si può imparare *leggendo il lavoro degli altri*, cosa che con le caselle di testo è impossibile per costruzione.

L'errore tipico è l'opposto: scaricare il flusso da quaranta riquadri visto in un video, vederlo fallire per un componente mancante, e concludere che è roba da specialisti. Quello era il punto di arrivo di qualcun altro. Nessuno impara l'impianto elettrico partendo dalla centralina di un albergo.

## Quando ha senso, e quando no

Se vi serve un'immagine ogni tanto per una presentazione, ComfyUI è sproporzionato: l'interfaccia con la casella fa il suo lavoro e non chiede niente in cambio. Il pareggio arriva con la **ripetizione**.

Trenta schede prodotto che devono avere lo stesso trattamento. Ritratti aziendali che devono somigliarsi fra loro. Una serie di illustrazioni che deve tenere uno stile riconoscibile per mesi, con la possibilità di rifarne una a marzo identica per impostazione a quella di novembre. Lì il flusso costruito una volta — salvato, versionato, riaperto — è un altro mestiere rispetto a riscrivere la frase e sperare che il caso restituisca lo stile della volta scorsa. Il flusso è la ricetta; la casella di testo era ordinare al ristorante.

E c'è il caso della riservatezza, che per i lettori di questo sito pesa: ComfyUI gira in locale, con modelli scaricati, e nessuna immagine va da nessuna parte. Bozzetti non pubblici, foto di persone, materiale di clienti: tutto resta sulla macchina. Per chi lavora su commissione non è una comodità, è una condizione.

## La parte che nessuno dice

Occupa spazio, e occupa tempo. I modelli pesano gigabyte e se ne accumulano a decine; i flussi si rompono quando un componente si aggiorna; ogni tanto si passa una sera a capire perché un'estensione non parte più, e la risposta è in una discussione su GitHub di tre settimane fa. Chi ve lo presenta senza questa parte vi sta vendendo qualcosa.

È il prezzo di avere l'impianto in vista invece che dietro il muro, ed è un prezzo onesto a patto di sapere cosa si sta comprando. Ma è anche il motivo per cui, dopo l'entusiasmo dei primi mesi, molti tornano alla casella di testo: non perché abbiano smesso di volere il controllo, ma perché fare l'elettricista tutte le sere non era il mestiere che avevano scelto.

## Il problema che resta aperto

Messa così, la scelta sembra secca: o la comodità senza controllo, o il controllo con la manutenzione. E per qualche anno lo è stata davvero.

La domanda interessante è se sia una scelta *necessaria*. Perché le due cose che ComfyUI vi dà — la trasparenza del procedimento e il fatto che tutto giri sul vostro computer — non dipendono dal fatto che l'interfaccia sia una scatola di cavi. Dipendono dall'architettura. La tela coi riquadri è un modo di mostrare la pipeline, ed è nato per gli sviluppatori perché i primi a volerla vedere erano loro; ma è un modo, non l'unico.

È esattamente la scommessa di **[Anymatix](https://www.anymatix.com/)**, il progetto a cui lavoro sotto il marchio [make become](https://make-become.github.io/): tenere il locale e il controllo, e togliere l'impianto dalla vista di chi non ha voglia di guardarlo — immagini, video, audio, sul proprio computer, senza abbonamenti e senza che i materiali escano di casa. Lo dico da parte in causa, e quindi prendetelo per quello che è: la ragione per cui ci lavoro è che ho passato troppe di quelle sere a capire perché un'estensione non partiva più, e la conclusione che ne ho tratto è che il costo era accidentale, non necessario.

Il che non toglie niente a quanto scritto sopra. Se volete *capire* come funziona la generazione di immagini, ComfyUI resta la strada più diretta che conosca, e resterà utile anche a chi poi userà altro: il pomeriggio passato a girare le manopole con il seed fermo è il pomeriggio in cui si smette di essere spettatori. Gli strumenti che nascondono l'impianto sono comodi in proporzione a quanto già sapete cosa c'è sotto.

## In sintesi

La casella di testo vi restituisce immagini. La tela coi riquadri vi restituisce anche il *perché*, e il perché è l'unica parte che si accumula: le immagini si buttano, il criterio con cui le giudicate no.

Poi, quando il criterio ce l'avete, potete legittimamente cercare uno strumento che vi risparmi i cavi. Ma in quell'ordine — prima capire, poi semplificare. Al contrario si ottiene solo una casella di testo più costosa.
