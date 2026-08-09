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

## «L'inglese è migliore» è una frase troppo larga

La lingua interviene in almeno quattro punti diversi: quantità e qualità dei testi di addestramento, tokenizzazione, dati di allineamento e benchmark usati durante lo sviluppo. Non segue che ogni domanda inglese riceva una risposta migliore. Un modello può ragionare bene in inglese e conoscere peggio una procedura amministrativa italiana; può tradurre perfettamente una frase e perdere la funzione pragmatica di una formula giuridica.

I benchmark multilingue più recenti cercano proprio di separare queste capacità. MMLU-ProX, pubblicato a EMNLP 2025, estende domande difficili a 29 lingue, italiano compreso, con traduzioni controllate e una valutazione della coerenza. I risultati non producono una classifica eterna: mostrano differenze fra modelli, materie e lingue. Un punteggio aggregato nasconde il caso che interessa a noi.

Il problema si vede bene con il diritto. Una domanda può richiedere insieme comprensione linguistica, conoscenza della giurisdizione e aggiornamento normativo. Tradurla in inglese può aiutare il ragionamento generale e peggiorare i termini d'arte. La soluzione non è scegliere una lingua una volta per tutte: è ancorare il lavoro a fonti italiane vigenti e chiedere che citazioni e terminologia restino nella lingua originale.

## Separare lingua di lavoro e lingua di consegna

Non devono coincidere. In una ricerca tecnica posso far formulare query inglesi, consultare documentazione internazionale e ricevere la consegna in italiano. In una revisione contrattuale posso mantenere testo, definizioni e riferimenti in italiano, chiedendo eventualmente un controllo logico in inglese in un passaggio separato.

Un prompt utile lo dice esplicitamente:

```text
Analizza le fonti nella lingua in cui sono pubblicate.
Conserva in italiano termini giuridici e citazioni della normativa.
Puoi usare l'inglese per cercare letteratura tecnica internazionale.
Consegna in italiano naturale, senza calchi; segnala i concetti per cui
la traduzione perde una distinzione rilevante.
```

Questo evita due errori opposti: limitare la ricerca al solo web italiano e importare lessico inglese dove esiste già un termine preciso.

## Come fare una prova che dica qualcosa

Cinque casi reali sono più informativi di cinquanta domande da quiz. Costruite una piccola matrice con le attività che contano: estrazione, sintesi, classificazione, ragionamento con vincoli, scrittura finale. Preparate per ciascuna lo stesso materiale e gli stessi criteri.

Confrontate tre condizioni:

1. domanda e risposta in italiano;
2. domanda in inglese, risposta in italiano;
3. analisi in inglese su fonti originali, revisione finale in italiano.

Valutate accuratezza, omissioni, terminologia, necessità di riscrittura e tempo totale. Fate giudicare le uscite senza mostrare quale condizione le ha prodotte. Se il modello è aggiornabile, annotate nome e data: una conclusione del 2024 può essere falsa per la versione del 2026.

Per la scrittura aggiungete un criterio che i benchmark ignorano: quanto il testo suona tradotto. Calchi come «fare senso», nominalizzazioni eccessive e sequenze di sostantivi possono rendere formalmente corretto un testo che nessun professionista italiano scriverebbe.

## La lingua influenza anche il comportamento sociale

La cortesia, il dissenso e l'intensità non si trasferiscono meccanicamente. Uno studio ACL del 2024 su prompt cortesi e scortesi in inglese, cinese e giapponese ha trovato che l'impolitenza tendeva a danneggiare le prestazioni, ma livelli maggiori di cortesia non producevano un miglioramento monotono e l'optimum cambiava per lingua. È un buon antidoto alle regole universali da social network.

Se il compito riguarda negoziazione, feedback, salute o assistenza al pubblico, testate anche la pragmatica: una risposta può essere fattualmente equivalente e socialmente inappropriata. Specificare destinatario, relazione e conseguenza desiderata conta più dell'inglese in sé.

## Una regola operativa

Partite nella lingua dei dati e del destinatario. Passate all'inglese quando serve accesso migliore a documentazione, terminologia tecnica o capacità di ragionamento osservata nel vostro test. Tornate all'italiano con una revisione dedicata, non con una traduzione alla cieca.

La domanda utile, quindi, non è «quale lingua parla meglio il modello?». È: in quale lingua sono le prove, le decisioni e le persone di questo lavoro?

## La mia esperienza vale meno della vostra mezz'ora

Nella mia esperienza, su testi da riassumere non cambia niente; su estrazione di dati strutturati cambia poco; su ragionamenti lunghi con vincoli multipli l'inglese è ancora davanti. Ma è la mia esperienza sui miei compiti, e vale meno di mezz'ora della vostra sui vostri.

## Fonti e approfondimenti

- Li et al., [MMLU-ProX: A Multilingual Benchmark for Advanced Large Language Model Evaluation](https://aclanthology.org/2025.emnlp-main.79/), EMNLP 2025.
- Yin et al., [Should We Respect LLMs? A Cross-Lingual Study on the Influence of Prompt Politeness on LLM Performance](https://aclanthology.org/2024.sicon-1.2/), ACL 2024.
- OpenAI, [Prompt engineering](https://platform.openai.com/docs/guides/prompt-engineering), documentazione ufficiale su istruzioni e contesto.
- Anthropic, [Multilingual support](https://docs.anthropic.com/en/docs/build-with-claude/multilingual-support), indicazioni operative sui compiti multilingue.
