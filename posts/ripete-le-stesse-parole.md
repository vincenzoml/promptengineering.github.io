---
title: Perché ripete sempre le stesse parole
description: "Fondamentale", "cruciale", "nel panorama attuale". C'è un lessico che tradisce un testo generato, e ha una spiegazione precisa. Come si riconosce, e come si esce dalla media.
date: 2026-04-28
author: vincenzo
tags: [stile, scrittura, prompt engineering]
image: /images/posts/cover-ripete-le-stesse-parole.png
lang: it
---

![Perché ripete sempre le stesse parole](/images/posts/cover-ripete-le-stesse-parole.png)

Da dove nasce il lessico riconoscibile dei testi generati, perché non basta chiedere "scrivi in modo naturale", e il metodo che funziona davvero per uscirne — che non è una lista di parole vietate, anche se quella aiuta.

Chi legge molti testi prodotti da un modello comincia a riconoscerli da lontano, e il segnale non è il contenuto: è il vocabolario. Ci sono parole che tornano sempre. "Fondamentale". "Cruciale". "Nel panorama attuale". "Non solo... ma anche". Le frasi che aprono con un participio. I paragrafi che finiscono con una riformulazione della prima frase.

Non è una firma nascosta. È aritmetica.

## La media di tutto

A ogni passo il modello sceglie la continuazione più probabile, e "probabile" significa: frequente nei testi su cui si è formato. Quei testi sono in larghissima parte scrittura pubblica, professionale, un po' formale — articoli, documentazione, materiale divulgativo, comunicati.

In quella massa, certe parole sono statisticamente dominanti. "Importante" è comune, ma "fondamentale" appare in modo sproporzionato nei testi che si prendono sul serio; e siccome il modello scrive testi che si prendono sul serio, "fondamentale" esce di continuo.

Il tono medio dell'italiano scritto pubblico è enfatico. Chiedendo a un modello di scrivere senza altre indicazioni, si riceve esattamente quello: enfasi come impostazione predefinita.

## Perché "scrivi in modo naturale" non funziona

Perché "naturale" è un aggettivo, e il modello lo interpreta come un'istruzione stilistica generica — di cui esistono, nei suoi dati, esempi mediocri quanti gli altri. Chiedere naturalezza a chi produce la media dà la media dei testi che si dichiarano naturali.

Vale lo stesso per "professionale", "coinvolgente", "diretto". Non sono istruzioni: sono desideri.

## Cosa funziona

**Le liste di divieti.** Poco elegante e molto efficace. "Non usare: fondamentale, cruciale, essenziale, panorama, ecosistema, sfida. Nessuna frase che cominci con un participio. Niente riepiloghi." Ogni divieto toglie una scorciatoia, e il modello deve trovare un'altra strada — che quasi sempre è più specifica, perché le parole vaghe sono le prime a essere vietate.

**Il registro dichiarato per esteso.** Non "scrivi in modo semplice", ma "scrivi come parleresti a un collega esperto davanti a un caffè: frasi corte, niente premesse, se una cosa è ovvia non dirla". Cinque righe di descrizione battono qualsiasi aggettivo.

**Gli esempi.** Il metodo migliore, e il più trascurato. Dategli due testi vostri — non descrizioni del vostro stile, i testi — e chiedete di scrivere così. Il modello estrae dal materiale reale molto più di quanto sappiate dire a parole del vostro modo di scrivere: la lunghezza tipica delle frasi, la punteggiatura, quanto usate le subordinate, quando fate una battuta.

**La revisione mirata.** Anche partendo bene, la seconda passata paga: "rileggi e togli tutte le parole che non aggiungono niente; accorcia le frasi più lunghe di venticinque parole". Su un testo esistente il modello è un ottimo editor, molto migliore di quanto sia autore.

## Il criterio finale

Il segnale più affidabile che un testo è stato prodotto senza indicazioni non è una parola particolare: è **che potrebbe averlo scritto chiunque**. Nessun dettaglio che solo voi conoscete, nessun caso specifico, nessuna opinione che qualcuno potrebbe contestare.

E allora la contromisura non è stilistica ma di sostanza: mettere nel testo qualcosa che il modello non poteva sapere. Un numero preso dai vostri dati. Una cosa che vi ha detto un cliente. Una volta in cui vi è andata male.

## Un'impronta statistica, non una prova forense

Liste di parole «da ChatGPT» circolano continuamente: *delve*, «cruciale», «panorama in evoluzione», «è importante sottolineare». Sono indizi utili per l'editing, pessimi per attribuire una paternità. Anche gli umani usano quelle parole; dopo che i cliché vengono pubblicamente denunciati, i modelli e i prompt cambiano.

La ricerca sul rilevamento mostra una gara instabile. Parafrasi, traduzione, editing umano e cambio di modello riducono l'affidabilità dei detector. Un classificatore può misurare somiglianza con i dati su cui è stato addestrato, non dimostrare chi ha scritto una pagina. In ambito scolastico o lavorativo, trattare il punteggio come prova può produrre falsi accusati.

Per un editore la domanda più utile è un'altra: quali passaggi non portano informazione?

## Perché nasce il lessico medio

Un prompt generico chiede al modello di campionare una risposta probabile per un pubblico non definito. Emergono formule frequenti, sicure e trasferibili. «Nel panorama attuale» apre qualsiasi tema; «fondamentale» segnala importanza senza doverla dimostrare; la conclusione ricapitola perché molti esempi di addestramento lo fanno.

L'allineamento aggiunge convenzioni di servizio: transizioni ordinate, tono positivo, equilibrio artificiale, disponibilità a continuare. Sono caratteristiche utili in chat e monotone in venti articoli consecutivi.

## Fare un inventario, non una lista nera

Prendete dieci testi e contate:

- aperture astratte prima del primo fatto;
- aggettivi di importanza privi di conseguenza;
- strutture ripetute fra sezioni;
- conclusioni che riassumono senza avanzare;
- coppie oppositive meccaniche;
- elenchi sempre della stessa lunghezza;
- metafore intercambiabili.

Poi costruite un *lint* editoriale. Non vieta automaticamente; segnala. Se «cruciale» introduce davvero la variabile da cui dipende un rischio, può restare. Se sparisce senza perdita, era aria.

## Il prompt che costringe a uscire dalla media

```text
Prima di scrivere, estrai dal materiale:
- cinque fatti che non appartengono a un'introduzione generica;
- due tensioni o risultati controintuitivi;
- una decisione che il lettore può prendere;
- i limiti delle fonti.

Costruisci ogni sezione attorno a uno di questi elementi.
Vieta frasi che dichiarano importanza senza specificarne l'effetto.
Non usare introduzione panoramica né riepilogo finale.
```

Il modello può comunque produrre manierismi. La differenza è che ora ogni paragrafo ha un debito informativo da pagare.

## Varietà non significa voce

Chiedere sinonimi o «burstiness» crea superficie irregolare, non autenticità. Una voce deriva da selezione: quali esempi meritano spazio, quale posizione viene difesa, quale dubbio rimane aperto. Anche una frase perfettamente imitata resta vuota se potrebbe comparire in un articolo opposto.

Gli studi sull'imitazione autoriale trovano proprio questo limite: i modelli riproducono meglio stili strutturati e segnali espliciti, peggio le sfumature implicite dei testi informali. L'editing deve quindi cercare non solo parole sospette, ma decisioni che nessuno ha preso.

## Una revisione in quattro colori

Segnate nel testo:

- **verde**: fatto verificabile o esempio originale;
- **blu**: inferenza necessaria fra fatti;
- **giallo**: orientamento utile al lettore;
- **rosso**: frase che potrebbe stare in qualunque articolo.

Eliminate il rosso, controllate il blu, citate il verde, accorciate il giallo. La percentuale di testo generato non conta; conta la densità di informazione difendibile.

## Un fatto vero dentro il testo

Un testo con dentro un fatto vero non somiglia più a nessun altro, quali che siano le parole.

## Fonti e approfondimenti

- Wang et al., [Catch Me If You Can? Not Yet](https://aclanthology.org/2025.findings-emnlp.532/), Findings of EMNLP 2025, sull'imitazione di stili impliciti.
- Sadasivan et al., [Can AI-Generated Text be Reliably Detected?](https://arxiv.org/abs/2303.11156), sui limiti teorici e pratici del rilevamento.
- OpenAI, [AI classifier no longer available due to low rate of accuracy](https://openai.com/index/new-ai-classifier-for-indicating-ai-written-text/), un caso documentato di ritiro di un detector.
- Baumler et al., [Can You Make It Sound Like You? Post-Editing LLM-Generated Text for Personal Style](https://aclanthology.org/2026.acl-long.2030/), ACL 2026.
