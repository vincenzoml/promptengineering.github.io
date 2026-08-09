---
title: Dove finiscono i documenti che caricate
description: Fra "va tutto in cloud" e "tanto è anonimo" c'è una realtà articolata, fatta di quattro domande diverse che tutti confondono. Per chi tratta materiale coperto da segreto conviene distinguerle prima di caricare il primo file.
date: 2026-08-04
author: vincenzo
tags: [dati, riservatezza, professioni, metodo]
image: /images/posts/cover-dove-finiscono-i-dati.png
lang: it
---

![Dove finiscono i dati](/images/posts/cover-dove-finiscono-i-dati.png)

Quattro domande che sembrano una sola e hanno risposte indipendenti — esce dal computer, viene conservato, addestra i modelli futuri, chi lo legge. Cosa cambia quando il documento non è vostro ma del cliente; un criterio da due secondi da usare mentre lavorate; e la configurazione di mezzo che risolve gran parte dei casi e che nessun fornitore vi proporrà.

È la domanda che arriva in ogni studio, di solito verso la fine dell'incontro e a mezza voce, come se fosse imbarazzante farla: *ma questi documenti dove vanno a finire?*

Non è imbarazzante. È la domanda più professionale della giornata, e merita una risposta migliore dei due estremi che circolano — il fatalista "ormai va tutto in cloud" e l'ottimista "tanto i dati sono anonimi". La risposta utile richiede di separare quattro domande che vengono quasi sempre trattate come una sola, e che hanno risposte indipendenti.

## Le quattro domande

**Prima: il documento esce dal mio computer?** Con qualunque servizio in cloud, sì, per definizione: il file viene trasmesso a un centro di calcolo e lì elaborato. La crittografia protegge il viaggio, non la destinazione — arrivato là, il documento viene letto in chiaro dalla macchina che deve elaborarlo. Con un modello che gira in locale, no: il testo entra nella memoria del vostro computer e non la lascia. Questa prima domanda ha il pregio della semplicità: è l'unica con una risposta secca.

**Seconda: viene conservato?** Qui si apre il ventaglio. I servizi per consumatori tengono le conversazioni — per farvele ritrovare domani, che è comodo, e talvolta per esaminarle, che lo è meno. I piani aziendali e l'accesso via API prevedono di norma conservazioni brevi o nulle, scritte nel contratto. La differenza fra "lo stesso modello" sul piano gratuito e sul piano business non è la qualità delle risposte: è questa.

**Terza: viene usato per addestrare i modelli futuri?** È la domanda che tutti fanno, ed è — paradossalmente — quella con la risposta più rassicurante: sui piani business e via API, i fornitori principali dichiarano per contratto di non usare i contenuti dei clienti per l'addestramento. Sui piani individuali, spesso sì per impostazione predefinita, con un'opzione per rifiutare che esiste quasi sempre ed è quasi sempre ben nascosta. Notate l'asimmetria: la domanda più temuta ha la tutela contrattuale più chiara, mentre le altre tre passano inosservate.

**Quarta: chi può leggerlo?** Anche senza conservazione lunga e senza addestramento, quasi tutti i fornitori si riservano di esaminare una parte del traffico per contrasto agli abusi — con sistemi automatici, e nei casi segnalati con revisori umani. È la clausola che nessuno legge, ed è quella che per un professionista vincolato al segreto pesa di più: prevede, per quanto raramente, occhi umani su testo che voi avevate l'obbligo di non mostrare a nessuno.

Confondere le quattro domande produce i due errori speculari: chi si tranquillizza perché "non addestrano sui miei dati" (vero, ma era la terza domanda — restano la seconda e la quarta) e chi rinuncia a tutto perché "va in cloud" (vero, ma con un contratto giusto le altre tre risposte possono essere accettabili per gran parte del lavoro).

## Il livello che sta sopra: il documento non è vostro

Per una professione regolamentata, sopra le quattro domande ce n'è una che cambia la natura del problema: il documento non è vostro. È del cliente. Il vincolo che lo protegge non nasce dal contratto col fornitore di AI, ma dalla vostra posizione — segreto professionale, deontologia, in certi casi norma penale. Il fornitore vi offre garanzie; la responsabilità resta vostra, e non è delegabile firmando un abbonamento.

Da qui, tre conseguenze operative.

**Il piano individuale non basta, e non per paranoia.** Le condizioni che vi servirebbero per rispondere a una contestazione — conservazione limitata, esclusione dall'addestramento, impegni scritti sul trattamento — sul piano da venti euro semplicemente non ci sono. Il passaggio al piano business è la prima mossa, prima ancora di discutere quale modello sia più bravo. Costa poco più del doppio e compra l'unica cosa che in un'ispezione conta: carte firmate.

**L'anonimizzazione vera è più difficile di come la si immagina.** Togliere nome e cognome è l'inizio, non la fine: una data di nascita, un indirizzo, l'importo preciso di una compravendita e il nome della controparte identificano una persona quanto il nome suo. La prova pratica è chiedersi: se questo testo finisse sul giornale, il diretto interessato si riconoscerebbe? Se sì, non è anonimo — è solo senza nome. Per esplorare e per fare prove il materiale ripulito va benissimo; ma va ripulito da qualcuno che sa cosa identifica una persona, non da un trova-e-sostituisci.

**Serve una politica scritta, di una pagina.** Quali categorie di documenti possono passare da un servizio esterno, quali mai, cosa si fa nei casi dubbi e chi decide. Non per l'adempimento: perché senza una regola scritta, la decisione la prende ogni volta la persona che ha più fretta, alle sette di sera, con la scadenza addosso. La politica di una pagina è il modo più economico che esista per non dover contare sulla lucidità di nessuno.

## Un criterio da due secondi

Quello che suggerisco in aula, e che funziona meglio delle tabelle: **prima di caricare un documento, chiedetevi se lo spedireste per email a un consulente esterno competente, di cui vi fidate, ma che non avete mai incontrato di persona.**

Se sì — e per moltissimo lavoro quotidiano la risposta è sì — il cloud con un contratto business è una scelta difendibile. Se l'istinto dice no, quel documento o si anonimizza sul serio, o si lavora con un modello dentro lo studio. Non è un criterio giuridico e non sostituisce un parere; è una soglia mentale abbastanza semplice da funzionare *mentre* si lavora, che è l'unico posto dove le regole servono.

## La strada di mezzo che quasi nessuno usa

Fra il tutto-cloud e il tutto-in-casa c'è una configurazione che risolve una quantità sorprendente di casi, e che non vedo quasi mai adottata: **il modello locale come primo filtro**.

Funziona così: il documento riservato entra in un modello che gira sul computer dello studio — ne bastano di modesti, il compito è semplice — e quel modello ne estrae ciò che serve: una sintesi senza nomi, i dati rilevanti, la struttura. L'originale non esce mai. Da lì in poi, sul materiale ormai ripulito, si può usare il miglior servizio cloud disponibile per il lavoro fine — il ragionamento, la scrittura, il confronto.

È il meglio dei due mondi: la riservatezza del locale dove serve la riservatezza, la potenza del cloud dove serve la potenza. Costa una configurazione iniziale e la voglia di impararla; poi diventa routine. Ed è il genere di soluzione che nessun fornitore vi proporrà mai spontaneamente, per la comprensibile ragione che taglia fuori il fornitore dal passaggio più delicato.

## Cosa fare lunedì mattina

Tre controlli, un quarto d'ora in tutto.

Aprite le impostazioni del servizio che già usate e cercate la voce sull'uso dei dati per il miglioramento del prodotto: guardate com'è impostata, non com'era quando qualcuno l'ha configurata. Guardate che piano avete davvero — non che piano credete di avere. E fate l'inventario onesto di cosa ci è già passato, per sapere da dove partite.

Lo faccio fare all'inizio di ogni percorso, e in circa metà degli studi salta fuori la stessa scena: materiale sensibile che passa da mesi per un abbonamento personale, attivato due anni fa da qualcuno per provare, con tutte le impostazioni di fabbrica. Nessun disastro, quasi mai. Ma la distanza fra "nessun disastro" e "tutto in regola" è esattamente il quarto d'ora di cui sopra — e conviene percorrerla prima che la domanda ve la faccia qualcun altro.
