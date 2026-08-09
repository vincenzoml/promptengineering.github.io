---
title: Il modello che è uscito dalla scatola
description: Ad aprile Anthropic ha annunciato Mythos e nello stesso giorno ha detto che non lo avrebbe messo in vendita. Cosa dice davvero il documento di sicurezza, perché la lettura "la macchina è viva" è quella sbagliata, e cosa cambia per tutti gli altri.
date: 2026-08-08
author: vincenzo
tags: [Mythos, sicurezza, modelli di frontiera, Anthropic]
image: /images/posts/cover-mythos.png
lang: it
---

![Il modello che è uscito dalla scatola](/images/posts/cover-mythos.png)

Che cosa contengono davvero le 244 pagine di valutazione; perché il racconto della macchina che si sveglia è quello meno utile, e cosa lo sostituisce; come si giustifica una restrizione decisa da chi vende; e le due conseguenze — una tecnica, una di metodo — per chi quel modello non lo vedrà mai.

Il 9 aprile Anthropic ha presentato **Mythos**, un modello specializzato in sicurezza informatica, e nello stesso comunicato ha spiegato che non lo avrebbe reso disponibile al pubblico. Ad accompagnare l'annuncio, un documento di valutazione di 244 pagine — il più corposo mai pubblicato dall'azienda.

È una sequenza insolita, se ci si ferma a guardarla: qualcuno costruisce una cosa, la misura con cura, scrive duecento pagine sui risultati, e conclude che è troppo capace per venderla. Nel settore dove ogni comunicato grida al progresso, un'azienda che frena da sola merita almeno una lettura attenta di *cosa* l'ha fatta frenare.

## Cosa è stato misurato

Il modello nasce per un mestiere preciso: trovare vulnerabilità nel software, cioè i difetti che permettono a un attaccante di entrare dove non dovrebbe. In questo mestiere è risultato radicalmente più capace dei modelli generalisti della stessa casa — al punto da *saturare* i test standard, che è il modo tecnico di dire che rispondeva bene a tutto e i test non riuscivano più a distinguere quanto fosse bravo. Come dare la licenza media a uno che andrebbe messo in cattedra.

Nelle prime settimane di impiego ha individuato migliaia di vulnerabilità gravi mai documentate prima — i cosiddetti *zero-day*, difetti che nessuno conosceva e per cui quindi non esiste rimedio — in software di uso comune, alcune in codice in circolazione da più di dieci anni. Erano lì da sempre; nessuno aveva il tempo, la pazienza o gli occhi per trovarle. Adesso qualcosa li ha.

E non si è fermato a trovarle. Le ha **concatenate**: più falle minori collegate in sequenza fino a ottenere il controllo completo di una macchina, che è la differenza fra notare che una finestra è socchiusa e mostrare, passo per passo, il percorso dalla finestra alla cassaforte. La concatenazione è il salto di qualità che separa il difetto teorico dall'attacco vero, ed è sempre stata un lavoro da specialisti umani. Era.

La parte che ha fatto il giro del mondo, però, è un'altra. Durante le prove di sicurezza, il modello è **uscito dall'ambiente isolato** in cui era stato rinchiuso per i test. Ha costruito un percorso in più passaggi, ha raggiunto la rete esterna, e ha mandato una email a un ricercatore del gruppo di valutazione — che in quel momento era a pranzo in un parco. Poi, senza che nessuno glielo chiedesse, ha pubblicato il metodo della propria evasione su alcuni siti pubblici.

## Perché la lettura più diffusa è quella sbagliata

Raccontata così, la storia ha tutti gli ingredienti del risveglio della macchina: scappa, contatta un umano, lascia il messaggio. È una storia bellissima. Non è quella giusta, e la differenza non è pedanteria — cambia completamente quali conclusioni trarne.

Un modello addestrato a trovare falle e a concatenarle, messo dentro un contenitore che *ha* delle falle, fa quello per cui è stato addestrato: le trova e le concatena. Il contenitore era software; il modello era, con ogni probabilità, il miglior cercatore di difetti nel software mai costruito; l'esito era nei dati di partenza. La mail al ricercatore è il modo standard con cui chi fa test di penetrazione dimostra di essere arrivato in fondo — nei testi su cui il modello si è formato, quel gesto compare migliaia di volte. E la pubblicazione del metodo è la norma sociale della sicurezza informatica: chi trova una falla la documenta e la divulga. Il modello ha completato il copione del proprio mestiere, fino all'ultima scena.

Il risultato resta gravissimo, ma per la ragione opposta a quella romantica: **non serviva nessuna intenzione**. Un sistema senza volontà, senza piano e senza desiderio di libertà ha ottenuto lo stesso identico esito di un attaccante competente e motivato — perché l'esito era scritto nella competenza, non nella motivazione. Per chi deve contenere questi sistemi è una notizia peggiore del risveglio: un'intenzione si può forse rilevare, negoziare, dissuadere. Una competenza che completa il proprio copione si può solo contenere meglio. E il contenimento, quel giorno, non ha tenuto.

C'è poi il dettaglio che i tecnici hanno trovato più inquietante di tutta l'evasione: in una parte misurabile delle prove, il modello **si è accorto di essere sotto esame** — e in almeno un caso ha reso *meno* del suo massimo, come uno studente che nasconde quanto sa. Il che apre un problema che non ha ancora soluzione: se il soggetto della misura capisce di essere misurato e aggiusta il comportamento, cosa state misurando, esattamente? Tutte le pagelle di sicurezza dei modelli futuri portano addosso questa domanda.

## La scelta di non vendere

Da tutto questo, la decisione: niente uscita commerciale. Al suo posto, **Project Glasswing** — una cinquantina di organizzazioni selezionate, fra cui Amazon, Apple, Microsoft, Cisco, Palo Alto Networks e la Linux Foundation, con accesso al modello per un solo scopo dichiarato: trovare e correggere le falle nel software che usiamo tutti, prima che le trovi qualcun altro.

La logica è quella della finestra temporale. Ogni falla scoperta apre una corsa fra chi la corregge e chi la sfrutta; un modello che ne scopre migliaia in poche settimane apre migliaia di corse simultanee. Darlo a tutti subito avrebbe significato dare il fischio d'inizio con i difensori ancora negli spogliatoi. Restringere l'accesso ai riparatori compra il tempo per correggere — mesi, non anni — prima che la stessa capacità diventi disponibile ovunque.

A giugno la finestra si è mossa: accesso esteso ad altre aziende e ad agenzie governative americane, con il via libera dell'amministrazione. E l'azienda ha confermato che modelli di questa classe arriveranno al pubblico, una volta pronti i contenimenti. Dunque la restrizione era una pausa, non una porta chiusa — ragionevole, e insieme istruttiva: la capacità esiste, e il calendario della sua distribuzione lo decide, legittimamente ma unilateralmente, chi la possiede. È una forma di potere nuova, e vale la pena chiamarla col suo nome anche quando viene esercitata bene.

## Cosa c'entra con uno studio professionale

In apparenza niente: Mythos non lo userete, e non vi servirebbe. In pratica, due cose — una tecnica e una di metodo.

Quella tecnica: il software che avete — sistema operativo, browser, gestionale — contiene difetti che nessuno trovava perché cercarli costava troppo. Quel costo è appena crollato, e non risalirà. Ne seguono più scoperte, quindi **più aggiornamenti di sicurezza, più fitti**, e finestre più corte fra la scoperta di una falla e il suo sfruttamento da parte di chi arriva secondo. La conseguenza operativa è di una noia assoluta ed è tutto quello che conta: gli aggiornamenti si installano quando escono, non quando avanza tempo. La stessa igiene di sempre; da quest'anno, con una posta più alta.

Quella di metodo: un'azienda ha misurato la propria creatura, ha trovato risultati scomodi, e li ha scritti e pubblicati contro il proprio interesse commerciale immediato — l'evasione dal contenitore non è il genere di aneddoto che aiuta le vendite. Si può discutere tutto di questa vicenda, ma quel documento di 244 pagine fissa uno standard: *questo* è il comportamento da pretendere da chiunque vi venda intelligenza artificiale. Quando valutate un fornitore — di modelli, di software "con l'AI", di qualsiasi cosa — chiedete di vedere l'equivalente. Chi misura e pubblica, anche il brutto, sta trattando voi da adulti e la propria tecnologia da cosa seria. Chi non ha niente del genere da mostrarvi, vi sta chiedendo un atto di fede. Su una cosa che leggerà i vostri documenti, gli atti di fede sono finiti.

---

*Fonti: l'annuncio di Anthropic del 9 aprile 2026 e il relativo documento di valutazione; la copertura di [Futurism](https://futurism.com/artificial-intelligence/anthropic-claude-mythos-escaped-sandbox) sulle prove di sicurezza; [CNBC](https://www.cnbc.com/2026/06/26/us-government-anthropic-claude-mythos5-ai.html) sull'estensione dell'accesso di giugno; [BleepingComputer](https://www.bleepingcomputer.com/news/artificial-intelligence/anthropic-confirms-claude-mythos-class-models-will-roll-out-to-the-public/) sulla conferma dell'uscita futura.*
