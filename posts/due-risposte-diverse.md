---
title: Perché la stessa domanda dà due risposte diverse
description: Non è memoria e non è un difetto: dentro la generazione c'è una dose di caso, e si regola. Cosa cambia fra una risposta creativa e una ripetibile, e quando serve l'una o l'altra.
date: 2026-06-09
author: vincenzo
tags: [temperatura, riproducibilità, metodo, LLM]
image: /images/posts/cover-due-risposte-diverse.png
lang: it
---

![Perché la stessa domanda dà due risposte diverse](/images/posts/cover-due-risposte-diverse.png)

Perché la stessa richiesta produce testi diversi a ogni giro, chi ha deciso che dovesse funzionare così, e come si ottiene invece una risposta ripetibile. Con l'avvertenza che conta davvero: dove la variabilità aiuta, e dove diventa un problema serio senza che ve ne accorgiate.

Capita a chiunque provi due volte. Stessa domanda, copiata identica, e la seconda risposta è diversa dalla prima. A volte migliore, a volte peggiore, quasi sempre riformulata. La reazione istintiva è sospettare che il modello si ricordi del giro precedente e stia cercando di non ripetersi. Non è così: ogni conversazione parte pulita, e il modello non sa che gliel'avete già chiesto.

La spiegazione sta un piano più sotto, nel modo in cui il testo viene prodotto.

## La scelta a ogni parola

Un modello linguistico non decide una risposta e poi la scrive. Procede un frammento alla volta, e a ogni passo calcola una classifica: dato tutto quello che c'è prima, quali sono le continuazioni più probabili. Dopo "il gatto è salito sul" la classifica avrà "tetto" in cima, "tavolo" poco sotto, "treno" più giù, e a scendere migliaia di alternative sempre meno plausibili.

Poi deve sceglierne una. E qui c'è il bivio: prendere sempre la prima, oppure **pescare** fra quelle in alto, con una probabilità proporzionale al punteggio.

Prendere sempre la prima sembrerebbe la scelta sensata. È invece quella che produce i testi peggiori: piatti, ripetitivi, con la tendenza fastidiosa a incastrarsi. Certi modelli, forzati a scegliere sempre il massimo, ricominciano a ripetere la stessa frase all'infinito. La lingua vera non è la sequenza delle parole più prevedibili — se lo fosse, sarebbe illeggibile.

Quindi si pesca. E siccome si pesca, due giri danno due testi.

## La manopola

La quantità di caso si regola, e il parametro si chiama **temperatura**. A zero il modello prende sempre il massimo: stesso ingresso, stessa uscita, ogni volta. Alzandola, la classifica si appiattisce e anche le opzioni improbabili entrano in gioco; oltre una certa soglia il testo sbanda, e a valori alti diventa un delirio grammaticalmente corretto.

Nelle interfacce da chat questa manopola non si vede: sta su un valore medio, scelto perché produce testo che suona bene. Chi accede via interfaccia di programmazione la trova esposta, insieme ad altri due o tre parametri che agiscono in modo simile.

Conoscerla serve anche a chi non può toccarla, perché spiega la fisionomia degli errori. Un modello che cita un riferimento normativo plausibile e inesistente non sta mentendo: sta pescando in una classifica dove quel riferimento aveva un punteggio decente, perché somiglia a mille riferimenti veri che ha letto.

## Quando la varietà è un problema

Per scrivere va benissimo. Anzi: se vi servono dieci varianti di un titolo, ripetere la stessa richiesta dieci volte funziona meglio che chiedere "dammene dieci" — le dieci in un colpo solo tendono a somigliarsi, perché il modello vede le prime mentre scrive le altre.

Diventa un problema in due casi.

Il primo è **la verifica**. Se controllate un risultato rifacendo la stessa domanda e ottenete una risposta diversa, non avete verificato niente: avete due opinioni della stessa fonte. È uno dei motivi per cui il controllo dei fatti si fa fuori dal modello.

Il secondo sono **le procedure ripetute**. Se avete costruito un'istruzione che estrae dati da un documento e la applicate a duecento documenti, la variabilità vuol dire che il duecentesimo può uscire in un formato leggermente diverso dal primo — una data scritta in un altro modo, una colonna in più. Chi automatizza abbassa la temperatura vicino a zero e accetta un testo più legnoso in cambio della prevedibilità. Con le chat il rimedio è più rozzo e funziona lo stesso: dare un esempio del formato voluto invece di descriverlo a parole.

## Una prova che costa cinque minuti

Prendete una richiesta che fate spesso e ripetetela tre volte in tre conversazioni separate. Non per scegliere la risposta più bella: per vedere **quanto** variano.

Se le tre sono sostanzialmente uguali, quella richiesta è solida. Se sono tre cose diverse, è troppo vaga — e il modello, dovendo riempire i vuoti, sta pescando anche sulle decisioni, non solo sulle parole.

La variabilità della risposta misura, abbastanza bene, l'ambiguità della domanda. È la diagnosi più economica che conosca, e nessuno la fa.
