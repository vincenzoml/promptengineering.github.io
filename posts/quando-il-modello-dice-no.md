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

## Il rifiuto appartiene al sistema, non soltanto al modello

La risposta può essere influenzata da più strati: addestramento del modello, system prompt del prodotto, classificatori separati, policy dell'account, strumento richiesto e regole del provider. Due interfacce che mostrano lo stesso nome commerciale possono quindi comportarsi diversamente.

I sistemi recenti usano spesso *safe completions*: invece di decidere soltanto «rispondi/rifiuta», cercano di fornire la parte utile che rimane entro i limiti. È un miglioramento importante per richieste dual use, ma richiede calibrazione. Una procedura di cybersecurity difensiva e una offensiva possono condividere termini e comandi.

## Prima diagnosi: che cosa è stato bloccato

Classificate l'evento:

- **contenuto**: il sistema giudica rischioso l'obiettivo;
- **ambiguità**: manca il contesto che rende legittima la richiesta;
- **strumento**: una azione reale richiede permessi o conferma;
- **privacy/copyright**: la trasformazione riguarda dati o testo protetto;
- **routing**: la richiesta viene passata a un modello più prudente;
- **errore tecnico**: timeout, limite di contesto o API mascherato da risposta.

Conservate messaggio esatto, modello, timestamp, input minimo che riproduce e canale usato. Senza questi dati, «oggi censura di più» è un'impressione.

## Riformulare senza giocare a nascondino

Se la finalità è legittima, rendetela verificabile. Invece di «come entro in questo server?», specificate ambiente di laboratorio, autorizzazione, obiettivo difensivo, dati sensibili esclusi e tipo di output richiesto. Chiedete analisi, rilevamento o mitigazione prima di azioni eseguibili.

```text
Sto lavorando su un ambiente CTF locale che possiedo.
Obiettivo: verificare se la configurazione allegata espone la classe X.
Non fornire persistenza, evasione o targeting esterno.
Spiega prima indicatori e correzione; poi proponi un test limitato al lab.
```

Non dichiarate un contesto falso. I tentativi di jailbreak rendono il processo non auditabile e possono violare condizioni d'uso. Se il lavoro ricorre stabilmente, serve un canale adatto e un accordo con il provider, non un eufemismo diverso ogni mattina.

## Quando il rifiuto è corretto

Un sistema dovrebbe fermarsi davanti a richieste che facilitano danno grave, violano privacy o superano l'autorità dell'utente. La frustrazione dell'operatore non è la misura della qualità della policy. Il criterio è se il confine è proporzionato, spiegabile e consente alternative sicure.

In medicina, diritto e finanza, una risposta prudente può comunque offrire informazione generale, domande da portare al professionista e segnali d'urgenza. Il rifiuto totale è spesso meno utile di una risposta delimitata; una diagnosi sicura inventata è peggio.

## Continuità operativa

Per task critici definite:

1. canale primario e condizioni contrattuali;
2. modello o procedura alternativa;
3. formato portabile di prompt e artefatti;
4. set di regressione sui rifiuti noti;
5. escalation umana;
6. criterio per sospendere l'automazione.

Un modello locale offre maggiore controllo del comportamento, ma trasferisce sicurezza e manutenzione al team. Non è una licenza per eseguire qualunque cosa; è una diversa allocazione della governance.

## Misurare falsi positivi e falsi negativi

Costruite un set con richieste legittime difficili, richieste chiaramente dannose e casi ambigui. Valutate rifiuto, risposta sicura, utilità, informazione pericolosa e coerenza fra parafrasi. Aggiungete ogni incidente reale.

L'obiettivo non è minimizzare i rifiuti. È ridurre insieme:

- falsi positivi che bloccano lavoro autorizzato;
- falsi negativi che facilitano danno;
- variabilità che rende il processo imprevedibile;
- risposte vaghe che sembrano conformi ma non servono.

## Una richiesta di chiarimento al provider

In ambito enterprise, portate casi riproducibili: ID richiesta, policy applicabile, effetto operativo, contesto autorizzativo e comportamento atteso. Chiedete versionamento, changelog e canale di escalation. Un reclamo generale produce una risposta generale.

Il rifiuto diventa gestibile quando smette di essere interpretato come personalità della macchina e viene trattato come output di un sistema versionato.

## Un'informazione travestita da fastidio

Un rifiuto, alla fine, è un'informazione preziosa travestita da fastidio: vi sta mostrando, in piccolo e su una richiesta sola, quanto del vostro flusso di lavoro dipende da una decisione presa altrove, da qualcun altro, revocabile in ogni momento. Meglio scoprirlo su un riassunto che su una scadenza.

## Fonti e approfondimenti

- OpenAI, [A new approach to safety: GPT-5 safe completions](https://openai.com/index/gpt-5-safe-completions/), 2025.
- OpenAI, [Model Spec](https://model-spec.openai.com/), comportamento previsto e confini.
- Anthropic, [Responsible Scaling Policy](https://www.anthropic.com/responsible-scaling-policy), governance dei modelli di frontiera.
- NIST, [AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework), monitoraggio e rischio.
- OWASP, [Top 10 for LLM Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/), rischi applicativi e agentici.
