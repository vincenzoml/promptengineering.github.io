---
title: I conti non tornano, e il motivo è interessante
description: Un sistema che discute di matematica a livello universitario e poi sbaglia una somma da terza elementare. Non è un paradosso, è la chiave per capire cosa avete davanti — e per fargli fare i conti nel modo giusto.
date: 2026-06-30
author: vincenzo
tags: [numeri, verifica, fondamenta, LLM]
image: /images/posts/cover-i-conti-non-tornano.png
lang: it
---

![I conti non tornano](/images/posts/cover-i-conti-non-tornano.png)

Perché un sistema che spiega l'analisi matematica sbaglia la somma di dodici fatture: i numeri trattati come parole, e cosa comporta. Che fisionomia ha l'errore e perché è difficile da vedere. Come si divide il lavoro fra il modello e una macchina che calcola davvero — e il criterio generale che se ne ricava per tutto il resto.

Un commercialista che seguo aveva fatto la prova più sensata del mondo: aveva dato a un modello un elenco di dodici fatture chiedendo il totale. Il modello ha risposto con un bel prospetto ordinato, la somma in grassetto, e un errore di trecento euro. "Ma come," mi ha detto, "questo discute di analisi matematica e sbaglia una somma?"

È la reazione giusta, ed è la domanda giusta. La risposta spiega più cose sul funzionamento di questi sistemi di qualunque definizione.

## Le parole non sono numeri

Un modello linguistico produce testo prevedendo, frammento dopo frammento, la continuazione più probabile di quello che ha davanti. Quando scrive "391" dopo "17 × 23 =", non ha eseguito una moltiplicazione: ha prodotto i caratteri "3", "9", "1" perché, dato tutto quello che ha letto nella sua vita, erano la continuazione più plausibile.

Per le operazioni che compaiono spesso nei testi — le tabelline, i numeri tondi, i calcoli celebri — la continuazione più plausibile coincide con il risultato giusto, e l'illusione regge. Per una somma di dodici importi con i centesimi, quella precisa sequenza di cifre non è mai apparsa in nessun testo del mondo. Il modello la *stima*, con lo stesso meccanismo con cui stima la parola successiva di una frase. E una stima di cifre, anche buona, ogni tanto sbaglia di trecento euro.

Ecco il punto che vale la pena fissare: **il modello tratta i numeri come parole**. Li conosce come conosce i nomi propri — per averli visti in giro — non come li conosce una calcolatrice, che li rappresenta e ci opera sopra. Per questo può spiegare magnificamente *come si fa* una somma e poi sbagliarla: la spiegazione è testo, e il testo è il suo mestiere; l'esecuzione è aritmetica, e l'aritmetica non abita lì.

C'è anche un dettaglio tecnico che peggiora le cose: i numeri vengono spezzati in frammenti secondo regole nate per le parole. "12.847,50" può diventare tre o quattro pezzi, tagliati in punti che non rispettano le colonne delle unità e delle decine. Fare aritmetica su quei pezzi è come fare la somma in colonna su un foglio tagliato a strisce e rimescolato.

## Dove sbaglia, esattamente

L'errore numerico dei modelli ha una fisionomia riconoscibile, e conoscerla aiuta a stanarlo.

**Sbaglia in mezzo, non ai bordi.** L'ordine di grandezza di solito è giusto, le prime cifre pure: è nel corpo del numero che la stima scivola. Il totale sbagliato di trecento euro su ventimila *sembra* giusto a colpo d'occhio — ed è questo che lo rende pericoloso. Un errore grossolano si vedrebbe; uno piccolo e ben vestito passa.

**Sbaglia di più quando i dati sono tanti e sparsi.** Dodici importi in una tabella pulita vanno meglio di dodici importi sparpagliati in tre pagine di testo, dove al problema aritmetico si somma quello di *trovare* i numeri — e capita che uno venga saltato, o letto due volte.

**Sbaglia in silenzio.** Una persona che non è sicura di una somma lo dice, o almeno esita. Il modello no: il totale sbagliato arriva con la stessa prosa sicura di quello giusto, dentro un prospetto ordinato che comunica affidabilità. La forma curata non è un indizio di correttezza. Con questi sistemi non lo è mai.

## La soluzione non è rinunciare, è spostare il lavoro

Sarebbe sbagliato concludere che i modelli non servono per i lavori con i numeri. Servono moltissimo — a patto di dividere i compiti secondo le nature.

**Il modello estrae e organizza, la macchina calcola.** La divisione giusta è questa: al modello il lavoro linguistico — trovare gli importi in un documento disordinato, capirli, incolonnarli — e all'aritmetica vera l'esecuzione. In pratica: "estrai tutte le fatture da questo documento in una tabella con data, numero e importo" e poi la somma la fa il foglio di calcolo. Il modello ha fatto la parte che il foglio di calcolo non sa fare; il foglio di calcolo fa la parte in cui il modello inciampa.

**Oppure: fategli scrivere il calcolo, non il risultato.** Molti sistemi oggi possono scrivere ed eseguire un piccolo programma per calcolare la risposta, ed è una svolta: il programma somma davvero, con l'aritmetica del computer, non con la statistica del testo. Quando lo strumento che usate offre l'analisi dati o l'esecuzione di codice, per i numeri conviene chiederla esplicitamente: "calcolalo eseguendo il codice, non a mente". La differenza di affidabilità è enorme, e da fuori si vede poco perché la risposta arriva comunque in bella prosa.

**E comunque: il totale si riscontra.** Per le cose che contano, un controllo di quadratura resta obbligatorio — lo sarebbe anche con uno stagista bravissimo. La buona notizia è che riscontrare è molto più veloce che rifare: il modello ha già trovato, estratto e incolonnato tutto; a voi resta la somma, che è il passaggio da trenta secondi.

## Il criterio generale che se ne ricava

Questa storia dei numeri è il caso più nitido di un principio che vale per tutto il lavoro con i modelli: **distinguere i compiti linguistici da quelli esatti**. Riassumere, riformulare, tradurre, trovare, spiegare: linguistici, ed è lì che il modello rende. Calcolare, contare, ordinare alfabeticamente, verificare date: esatti, e vanno o delegati a uno strumento esatto o riscontrati a mano.

Il tranello è che il modello non rifiuta mai i compiti esatti. Li accetta con entusiasmo e li svolge con la sua unica arte, che è la plausibilità. Quando va bene, la plausibilità coincide con l'esattezza. Il vostro mestiere, usandolo, è sapere quando la coincidenza non è garantita.

Il commercialista delle dodici fatture, oggi, lavora così: il modello gli trasforma la carta in tabelle, il gestionale fa i conti. Dice che non è mai stato così veloce. I trecento euro non sono più tornati.
