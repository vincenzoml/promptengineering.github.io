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

## Il campionamento, in concreto

Il modello non recupera una frase già scritta. A ogni passo assegna probabilità ai possibili token successivi e una procedura di campionamento ne sceglie uno. La scelta modifica il contesto per il passo dopo. Differenze minime all'inizio possono quindi produrre paragrafi diversi.

I parametri più noti sono **temperature** e **top-p**. La temperatura ridistribuisce le probabilità: valori bassi concentrano le scelte sui token più probabili, valori alti allargano le alternative. Top-p limita la scelta al più piccolo insieme di token la cui probabilità cumulativa supera una soglia. Le API consigliano in genere di modificare uno dei due, non entrambi senza una ragione.

La temperatura non è un comando «creatività». Su un'estrazione strutturata un valore alto aumenta soprattutto errori e variazioni; su una sessione di ideazione può evitare che tutte le proposte cadano nello stesso solco. Il parametro regola il campionamento locale, mentre la qualità creativa dipende da materiale, criteri e selezione.

## Perché anche zero può non essere identico

Temperatura zero riduce il caso ma non sempre garantisce riproducibilità bit per bit. Infrastruttura, batching, kernel numerici, aggiornamenti del modello e tie fra token quasi equivalenti possono cambiare l'uscita. Alcune API offrono un seed e un identificatore della configurazione backend; anche in quel caso parlano di riproducibilità «best effort».

Se una procedura deve essere auditabile, salvate:

- provider, modello e versione o snapshot;
- prompt completo e ordine dei messaggi;
- parametri di campionamento e seed, se disponibile;
- risultati degli strumenti e fonti;
- data, output e codice che lo elabora.

Conservare soltanto la domanda non basta. Un motore di ricerca interrogato una settimana dopo può restituire pagine diverse; una tool call può incorporare l'ora corrente; un system prompt del prodotto può essere aggiornato.

## Stabilità semantica e identità testuale

Due risposte possono usare parole diverse e sostenere la stessa conclusione. Al contrario, due testi quasi identici possono differire in una negazione o in un numero. La metrica dipende dal lavoro.

Per classificazione ed estrazione si confrontano campi, tipi e valori. Per codice si eseguono test e controlli statici. Per analisi si estraggono tesi, prove, assunzioni e decisioni. La distanza fra stringhe raramente è la misura giusta.

Un test utile chiede cinque esecuzioni e costruisce una tabella:

| Elemento | Sempre presente | Variabile | In conflitto |
|---|---:|---:|---:|
| conclusione | | | |
| numeri | | | |
| fonti | | | |
| eccezioni | | | |

La colonna «in conflitto» conta più della varietà stilistica.

## Usare la variabilità invece di combatterla

Per un compito aperto, generate alternative in parallelo e poi valutatele con criteri espliciti. Non chiedete al primo campione di essere anche giudice definitivo. Per un compito chiuso, riducete gradi di libertà: schema JSON, vocabolario ammesso, esempi, controlli e retry mirato sui soli campi non validi.

La dispersione può stimare fragilità, ma con cautela. Se dieci campioni concordano, possono condividere lo stesso errore. L'incertezza del modello non è calibrata automaticamente sulla verità. Serve comunque una fonte o un test esterno.

## Un protocollo per produzioni ripetibili

1. fissare modello e parametri;
2. rendere esplicito ogni dato variabile;
3. chiedere output strutturato;
4. validare sintassi e invarianti con codice;
5. ritentare solo gli errori recuperabili;
6. conservare prompt, strumenti e artefatti;
7. rivalidare dopo ogni aggiornamento del provider.

La stessa domanda non deve necessariamente produrre le stesse parole. Deve produrre un risultato che soddisfa gli stessi invarianti. È questa la riproducibilità che vale nel lavoro.

## La diagnosi più economica che conosca

La variabilità della risposta misura, abbastanza bene, l'ambiguità della domanda. È la diagnosi più economica che conosca, e nessuno la fa.

## Fonti e approfondimenti

- OpenAI, [Text generation](https://platform.openai.com/docs/guides/text-generation), documentazione su generazione e parametri.
- OpenAI, [API reference](https://platform.openai.com/docs/api-reference/responses), per parametri e metadati correnti.
- Holtzman et al., [The Curious Case of Neural Text Degeneration](https://arxiv.org/abs/1904.09751), sul nucleus sampling.
