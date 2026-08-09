---
title: Quando il modello dice no
description: Un rifiuto non è un guasto e non è quasi mai una censura mirata. Come nascono, perché sono incoerenti, perché colpiscono proprio i mestieri seri, e cosa fare quando arrivano su una richiesta legittima.
date: 2026-07-21
author: vincenzo
tags: [rifiuti, limiti, metodo, LLM]
image: /images/posts/cover-quando-il-modello-dice-no.png
lang: it
---

![Quando il modello dice no](/images/posts/cover-quando-il-modello-dice-no.png)

Da dove nasce un rifiuto, perché è statistico e non regolamentare, e perché per questo colpisce proprio chi ha le ragioni più solide per chiedere. Le quattro mosse che funzionano, in ordine di efficacia — e la cosa che riguarda chiunque appoggi una pratica ricorrente su uno strumento che qualcun altro può ritarare stanotte.

Capita a tutti, prima o poi. Chiedete una cosa del tutto normale — riassumere un atto, impostare una diffida, analizzare una perizia medica — e il modello risponde che non può aiutarvi. Nessun errore tecnico, nessuna spiegazione utile: una formula educata, un invito a rivolgervi a un professionista (che magari siete voi), e la conversazione si ferma lì.

La reazione istintiva è pensare a una censura: qualcuno ha deciso che di questo argomento non si parla. Quasi sempre non è così, e capire cosa succede davvero cambia il modo di reagire — e toglie anche un po' di quella sensazione sgradevole di essere stati scambiati per malintenzionati.

## Da dove viene il no

Dopo l'addestramento principale, i modelli passano una seconda fase in cui vengono orientati verso i comportamenti che il fornitore considera desiderabili. Il metodo varia da casa a casa, ma la sostanza è simile: si mostrano al modello moltissimi esempi di risposte migliori e peggiori, e il modello impara a somigliare alle prime.

Fra gli esempi ci sono i rifiuti: richieste che vanno declinate, e il tono con cui declinarle. Il punto cruciale è *come* il modello assimila la lezione. Non c'è un elenco di argomenti proibiti consultato prima di rispondere, non c'è un registro che dice "diffide: no". C'è **una tendenza appresa**, spalmata negli stessi miliardi di parametri che generano tutto il resto — la stessa materia di cui è fatta la sua conoscenza dell'ortografia e del diritto societario.

Da qui discende tutto ciò che rende i rifiuti così sconcertanti.

Sono **statistici**: il modello non verifica una regola, valuta quanto la vostra richiesta *somigli* a quelle che ha imparato a declinare. Sono **sensibili alla forma**: la stessa domanda posta in due modi diversi può passare o non passare, perché una formulazione cade più vicina degli esempi di rifiuto e l'altra più lontana. Sono **contestuali**: la stessa frase dentro una conversazione tecnica ben avviata e dentro una conversazione partita male ottiene esiti diversi, perché il modello legge tutto, non solo l'ultima riga. Ed è per questo che l'esperienza è così incoerente — ieri sì, oggi no, al collega sì, a voi no. Non è malafede: è varianza.

C'è poi una seconda linea di difesa, separata dal modello: molti servizi affiancano dei **filtri** che leggono quello che entra e quello che esce, e possono troncare la conversazione a prescindere da cosa il modello avrebbe risposto. Quando la risposta si interrompe a metà frase, o sparisce dopo essere apparsa, di solito è questo. Riconoscerlo aiuta: è un meccanismo diverso, e reagisce a cose diverse.

## Perché colpisce proprio il lavoro serio

Il problema pratico è che le professioni legittime frequentano lo stesso vocabolario delle richieste pericolose, e il meccanismo lavora sul vocabolario.

Un penalista parla di reati tutto il giorno. Un medico legale descrive lesioni con precisione anatomica. Un consulente del lavoro tratta licenziamenti, contestazioni, conflitti. Un perito assicurativo ricostruisce incendi e frodi. Chi fa sicurezza informatica passa la giornata a descrivere attacchi, perché difendere significa esattamente questo. Nessuno di loro sta chiedendo qualcosa di illecito — ma le *parole* sono quelle, e per un sistema che decide per somiglianza, la somiglianza c'è.

Il falso positivo, quindi, non è un incidente che la prossima versione sistemerà. È **strutturale**: il costo di un sistema che decide per approssimazione su miliardi di richieste. Le tarature migliorano, i casi limite si spostano, ma il professionista che lavora su materia delicata resterà sempre più vicino al confine dell'utente medio.

E vale il contrario, che si dice meno volentieri: la stessa approssimazione *lascia passare* cose che non dovrebbero. Un modello che vi ha detto sì non vi ha autorizzati, non ha verificato la vostra deontologia, non ha valutato niente. Ha solo trovato la vostra frase abbastanza lontana dai suoi esempi di rifiuto. Il sì e il no hanno esattamente lo stesso peso morale: nessuno.

## Cosa fare, in ordine di efficacia

La prima mossa è la più efficace e la più trascurata: **dire perché state chiedendo**. Non come formula magica da recitare, ma perché è un'informazione vera che cambia il quadro statistico. «Sto redigendo una consulenza tecnica di parte in un procedimento civile; dal referto allegato mi serve la descrizione clinica delle lesioni» è, per il meccanismo che abbiamo visto, una richiesta *diversa* da «descrivi queste lesioni» — cade in un'altra regione, quella delle conversazioni professionali, dove gli esempi di rifiuto sono radi. Il contesto che diamo per scontato perché "tanto si capisce" è precisamente quello che il modello non ha.

La seconda: **riformulare, non insistere**. Ripetere la stessa frase con più forza non serve — il modello non si è offeso e non cambia idea, perché non ha idee. Cambiare inquadramento sì. Spesso funziona spostarsi dal caso al procedimento: non «scrivimi la diffida per Tizio», ma «quali elementi deve contenere una diffida per questo tipo di inadempimento, e in che ordine» — e il passo dal procedimento al testo lo fate voi, che è comunque il modo giusto di lavorare.

La terza: **spezzare**. Una richiesta che tocca tre argomenti sensibili insieme somiglia agli esempi di rifiuto più di tre richieste separate che ne toccano uno ciascuna. Non è un trucco per eludere: è la stessa ragione per cui una domanda confusa riceve risposte confuse. La granularità aiuta il modello a vedere cosa gli state chiedendo davvero.

La quarta: **cambiare strumento**. Le tarature differiscono da fornitore a fornitore più di quanto si creda, e su un dominio specifico uno può risultare sereno dove un altro è nervoso. Chi lavora stabilmente su materia delicata finisce quasi sempre per tenere due strumenti in rotazione, e non è uno spreco: è ridondanza, la stessa che si tiene per la connessione o per i backup.

Quinta, per completezza: se il blocco è del filtro esterno — la risposta troncata — riformulare nella stessa conversazione serve poco, perché il filtro rilegge tutto il contesto ormai segnato. Conversazione nuova, formulazione nuova.

## La cosa da mettere in conto

C'è un punto che sta sopra tutti i consigli, e riguarda chi costruisce abitudini di lavoro su questi strumenti: **la taratura è del fornitore, e il fornitore la cambia quando crede, senza avvisare**.

Un flusso che oggi passa può smettere di passare dopo un aggiornamento che non avete chiesto. Non per cattiveria: perché un caso di cronaca ha fatto stringere una maglia, e la vostra pratica abita accanto a quella maglia. È già successo, risuccederà, e non c'è preavviso perché le tarature di sicurezza sono, comprensibilmente, l'ultima cosa che un fornitore documenta nel dettaglio.

Le conseguenze operative sono due. **Nessun procedimento critico su un solo fornitore** senza sapere cosa fareste il giorno del blocco — la risposta può essere semplice come "abbiamo anche l'altro abbonamento". E **se il vostro lavoro sta stabilmente su materia delicata, guardate i modelli che girano in casa**: un modello locale ha la taratura del giorno in cui l'avete scaricato, per sempre. Nessuno la stringe mentre dormite.

Un rifiuto, alla fine, è un'informazione preziosa travestita da fastidio: vi sta mostrando, in piccolo e su una richiesta sola, quanto del vostro flusso di lavoro dipende da una decisione presa altrove, da qualcun altro, revocabile in ogni momento. Meglio scoprirlo su un riassunto che su una scadenza.
