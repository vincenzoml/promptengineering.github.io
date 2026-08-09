---
title: In che lingua conviene parlargli
description: L'inglese resta avanti, di poco e non ovunque. Dove l'italiano perde davvero, perché sui testi giuridici italiani serve cautela, e quando ha senso cambiare lingua a metà lavoro.
date: 2026-04-21
author: vincenzo
tags: [italiano, lingue, metodo, LLM]
image: /images/posts/cover-che-lingua-parla-meglio.png
lang: it
---

![In che lingua conviene parlargli](/images/posts/cover-che-lingua-parla-meglio.png)

Quanto sia vero che i modelli "pensano in inglese", dove il divario si sente e dove è sparito, il caso specifico dei testi giuridici italiani, e la tecnica di lavorare in due lingue nella stessa conversazione — che sembra una stranezza da smanettoni e non lo è.

Gira la convinzione che convenga scrivere in inglese ai modelli. Come tutte le mezze verità, ha una parte vera che è utile isolare.

## Cosa c'è di vero

I dati di addestramento sono in maggioranza in inglese, con un margine grande. E la tokenizzazione — il modo in cui il testo viene spezzato in frammenti — è stata costruita soprattutto su quello: l'italiano si frantuma in più pezzi a parità di contenuto, il che significa un po' più costo e un po' meno spazio utile nel contesto.

Per i compiti che richiedono ragionamento spinto, un divario misurabile esiste ancora, ed è più marcato sui modelli piccoli. Un modello leggero che in inglese se la cava, in italiano può inciampare.

## Cosa non è più vero

Per l'uso normale — riassumere, riformulare, estrarre dati, rispondere a domande su un documento — sui modelli di fascia alta la differenza è impercettibile. Se la vostra impressione è che in italiano "capisca meno", nove volte su dieci il problema è la richiesta, non la lingua.

E c'è un punto che le classifiche non misurano: **la vostra precisione**. Se scrivete in inglese senza padroneggiarlo, le vostre istruzioni saranno più povere, più generiche, più ambigue. Un modello leggermente più forte in inglese che riceve istruzioni scritte peggio produce risultati peggiori. Il calcolo, per la maggior parte dei professionisti italiani, finisce a favore dell'italiano.

## Il caso dei testi giuridici italiani

Qui serve cautela vera, e per una ragione che non è linguistica.

Il modello ha visto meno diritto italiano che diritto americano, molto meno. Sui riferimenti normativi la conseguenza è concreta: articoli plausibili ma sbagliati, numerazioni verosimili e inesistenti, sentenze inventate con estremo garbo. Non perché non capisca l'italiano — perché non ha memorizzato quel corpus con la stessa densità.

La contromisura è la stessa che vale per tutta la materia che cambia: **non chiedetegli la norma, dategliela**. Incollato il testo, il modello lo legge, lo applica e lo confronta benissimo. È un ottimo lettore di diritto italiano e un pessimo repertorio di diritto italiano, e la differenza fra i due usi separa chi ci lavora bene da chi si è preso uno spavento.

## Lavorare in due lingue

C'è una tecnica che uso spesso e che conviene conoscere: **le istruzioni in una lingua, il testo nell'altra**.

"You are reviewing an Italian contract. Extract every deadline with its article number. Answer in Italian." Le istruzioni in inglese cadono nella regione dove il modello è più preciso; il documento resta in italiano perché è in italiano; la risposta arriva in italiano perché serve a voi.

Non è indispensabile. Su compiti complessi, con modelli non di primissima fascia, la differenza si sente. E costa niente provare: stessa richiesta nelle due forme, risultati affiancati, dieci minuti.

Vale anche una variante più semplice e molto efficace: chiedere il ragionamento in inglese e la stesura in italiano. Il modello ragiona dove ragiona meglio e scrive dove scrivete voi.

## La prova che vale per il vostro caso

Le classifiche generali dicono poco del vostro lavoro. Prendete i tre compiti che fate più spesso, formulateli nelle due lingue, e confrontate su cinque casi reali.

Nella mia esperienza, su testi da riassumere non cambia niente; su estrazione di dati strutturati cambia poco; su ragionamenti lunghi con vincoli multipli l'inglese è ancora davanti. Ma è la mia esperienza sui miei compiti, e vale meno di mezz'ora della vostra sui vostri.
