---
title: Passare il lavoro a un'altra chat senza ricominciare
description: I crediti finiscono a metà lavoro, o volete continuare da terminale quello che avete cominciato nell'app desktop. Le conversazioni con Claude sono file sul vostro disco, e un'altra sessione può leggerle.
date: 2026-08-15
author: vincenzo
tags: [agenti, Claude Code, contesto, metodo, token]
image: /images/posts/cover-passare-il-lavoro-a-un-altra-chat.png
lang: it
---

![La domanda «stampa il path di questa conversazione» e il percorso del trascritto che l'agente risponde](/images/posts/cover-passare-il-lavoro-a-un-altra-chat.png)

Succede sempre nel punto peggiore. Sono le sette di sera, la conversazione dura da tre ore, e finalmente il modello ha capito com'è fatto il vostro lavoro: quali documenti contano, dove sono le insidie, che cosa non si tocca. E arriva il messaggio sui limiti d'uso. Oppure la conversazione è diventata così lunga che ogni risposta costa una fortuna e arriva piano. Oppure, più semplicemente, avete cominciato in Claude e volete continuare in un'altra applicazione.

La reazione istintiva è aprire una chat nuova e riassumere a mano: «stavamo facendo questo, avevamo deciso quest'altro». Si perde mezz'ora e si perdono i dettagli, che sono esattamente la parte che l'agente aveva imparato e voi no.

Non serve. **Quelle tre ore non sono evaporate: sono un file sul vostro disco.**

## Dove stanno davvero le conversazioni

Claude Code scrive ogni sessione in un file di testo, in una cartella che prende il nome dalla directory in cui state lavorando, con le barre trasformate in trattini:

```text
~/.claude/projects/-Users-nome-repos-progetto/<id-sessione>.jsonl
```

L'estensione `.jsonl` sta per *JSON Lines*: un oggetto JSON per riga, uno per ogni messaggio, chiamata di strumento e risultato. È leggibile con qualunque cosa legga testo — `grep`, `tail`, un editor, un altro agente.

L'applicazione desktop tiene un registro parallelo. Ogni sessione ha un file di metadati:

```text
~/Library/Application Support/Claude-Work/claude-code-sessions/…/local_<id>.json
```

Dentro ci sono il titolo della conversazione, la directory di lavoro, la data dell'ultima attività, il modello usato. E un campo che vale più degli altri: `cliSessionId`, che è il nome del file `.jsonl` corrispondente. **È il ponte fra le due applicazioni**: da una conversazione avuta nell'app desktop si risale al suo trascritto completo, quello che una sessione da terminale può leggere.

La cosa che mi ha sorpreso è che i percorsi non sono nemmeno uguali fra un'applicazione e l'altra. Ho chiesto a una conversazione dell'app dove stesse il proprio file, e la risposta non somigliava a nessuna delle due qui sopra:

```text
/var/folders/fy/30_kjq…/T/claude-hostloop-plugins/d42691f3…/projects/
  -Users-vincenzo-Library-Application-Support-Claude-local-agent-mode-…/
  cc0c87a4-dac7-4a53-9720-34496a3f3d86.jsonl
```

Il file c'è davvero — l'ho aperto, 1,3 MB — ma `/var/folders/…/T/` **è la cartella temporanea di sistema**, quella che macOS ripulisce per conto suo. Una conversazione di tre ore può stare in un posto che nessuno vi ha promesso di conservare.

Ho verificato tutto questo il 15 agosto 2026, con Claude Code 2.1.227 su macOS. Sono dettagli implementativi e non un'interfaccia pubblica: cambiano fra le versioni, cambiano fra le applicazioni, e su Linux o Windows sono altrove. Ed è esattamente per questo che il primo passo non consiste nell'imparare a memoria un percorso.

## Primo passo: farsi dare l'indirizzo

E come si fa a sapere percorsi così complicati? Non si fa: **ci pensa l'AI.** È una regola d'oro che vale ben oltre questo caso — se non sapete fare una cosa, fatela fare all'AI, anche mentre le state già facendo fare qualcos'altro.

Basta chiederlo alla conversazione stessa, finché risponde.

```text
Qual è il file su disco di questa conversazione? Stampami il percorso
completo, non aprirlo.
```

Funziona perché l'agente il proprio percorso ce l'ha, e ve lo dà in due secondi. È così che ho scoperto la cartella temporanea di poco fa: non l'ho cercata, me la sono fatta dire.

Per una domanda del genere conviene passare al modello più economico che avete, e alla risposta rapida. Sarebbe uno spreco pagare il modello più capace per farsi leggere un indirizzo — controllate quale è selezionato prima di premere invio.

Quel «non aprirlo» non è pignoleria. Un agente a cui chiedete un file tende ad aprirlo per essere utile, e su una conversazione lunga significa infilarsi decine di megabyte nel contesto — proprio quello che state cercando di evitare.

Se invece i crediti sono finiti e la conversazione non risponde più, il primo passo lo fa qualcun altro: un'altra sessione, magari su un altro account, o l'agente di un altro fornitore. Sono file di testo su un disco, non un formato proprietario.

```text
Cerca sul disco le conversazioni salvate da Claude.
Elencami le dieci più recenti con: titolo, data dell'ultima modifica,
dimensione e percorso. Non leggere i file interi.
```

Non serve dirgli dove guardare: i modelli più capaci sanno già dove quelle cartelle stanno, e quando non lo sanno lo cercano. Serve invece qualcosa per riconoscere la conversazione giusta, perché la data non basta quando ne avete tre aperte sullo stesso lavoro. Il titolo di solito è sufficiente — è quello che vedete nell'elenco delle conversazioni.

## Secondo passo: leggerla senza ingoiarla

Qui vale la stessa regola di un [prompt che uso da mesi per far spendere meno all'agente](#/post/quiet-mode-agenti-coding): **quasi tutta la spesa se ne va nel materiale che l'agente si trascina dietro mentre lavora**, e quel materiale va filtrato vicino alla sorgente.

Un trascritto di una sessione lunga è enorme, e la ragione è che contiene tutto: ogni file che l'agente ha aperto, ogni output di test, ogni diff, ogni riga di log. La conversazione che ricordate voi è una frazione minuscola di quel file.

A titolo di esempio, ho misurato una lunga sessione di brainstorming — quella da cui è nato, fra le altre cose, anche questo articolo.

| | |
|---|---|
| File completo | 55,5 MB — 2.915 righe |
| Soli messaggi che ho scritto io | 63,7 KB — 93 messaggi |
| Rapporto | circa 1 a 890 |

Novantatré messaggi. Tutto il resto — il 99,9% — è il mestiere dell'agente: documenti aperti, comandi eseguiti, risultati. Materiale che è servito in quel momento e che chi arriva dopo può comunque andarsi a rileggere quando gli serve. Quello che non deve fare è ingoiarselo tutto insieme: i prompt che seguono lavorano come un indice, servono a mappare il materiale e a pescarne solo i pezzi utili.

Alla sessione nuova, quindi, si chiede qualcosa di più preciso di «leggi la conversazione»:

```text
Il file <percorso> è il trascritto di una sessione precedente. È troppo
grande per aprirlo: non farlo.

1. Usa strumenti di ricerca testuale e analizza la conversazione senza
   leggerla tutta, per risparmiare token, crediti e contesto. Prendi in
   considerazione soprattutto gli ultimi messaggi.
2. Riassumimi: obiettivo, cosa è già fatto, decisioni prese e perché,
   cosa era rimasto aperto.

Poi fermati e aspetta conferma prima di toccare qualcosa.
```

L'ordine conta. **Gli ultimi messaggi** dicono dove eravate. **La ricerca testuale** recupera i punti di svolta, che stanno sparsi nel mezzo e sono quelli che un riassunto perde per primi. **Il riassunto** arriva alla fine, quando l'agente ha già in mano le due cose precedenti.

Il prompt è personalizzabile, ovviamente: se quello che vi serve è ritrovare una decisione precisa, chiedetegli di cercare quella.

L'ultima riga è la più importante. **Un agente che ha appena letto un riassunto del proprio predecessore è pericolosamente sicuro di sé: sa cosa stavate facendo, non sa cosa avete deciso di *non* fare.** La conferma serve a voi per correggere il riassunto mentre costa poco.

## Perché non basta /compact

Claude Code ha un comando, `/compact`, che riassume la conversazione in corso e libera contesto. È la cosa giusta nel caso ordinario: siete nella stessa sessione, volete continuare, il riassunto lo fa il modello che c'era.

Non copre i tre casi da cui siamo partiti. Non serve se la sessione è finita e non risponde più. Non attraversa le applicazioni. E non attraversa i fornitori: il file su disco lo legge chiunque, `/compact` è dentro un solo strumento.

C'è anche una differenza di controllo. `/compact` decide da solo cosa tenere. Leggendo il trascritto decidete voi cosa cercare — e se il vostro problema era una decisione presa due ore prima, sapete quale parola cercare meglio di qualunque riassunto automatico.

## Dove questo metodo si rompe

Quattro modi, tre dei quali li ho incontrati.

**Il trascritto può non esserci, o sparire.** Nessuna applicazione è perfetta, le politiche di archiviazione cambiano, e una parte di questi file vive nella cartella temporanea di sistema, che viene ripulita senza chiedere permesso. Da cui la regola pratica: quando una conversazione è andata bene e vi servirà, **fatevene salvare una copia** in una cartella vostra il giorno stesso. Potete chiederlo alla conversazione stessa, prima di chiuderla.

**Dentro c'è tutto, comprese le cose che non volete dare in giro.** Un trascritto contiene i file che l'agente ha aperto. Se in tre ore ha letto un `.env`, una chiave API o dati di un cliente, quella roba è in chiaro dentro il file. Prima di passarlo a un agente di un altro fornitore conviene guardarlo in faccia per quello che è: il registro completo di tutto ciò che è passato dallo schermo in quelle ore. Vale in particolare per chi lavora su [materiale coperto da segreto professionale](#/post/dove-finiscono-i-dati).

**Il riassunto è una perdita, non una copia.** L'agente nuovo non c'era. Non ha il ricordo del vicolo cieco di due ore prima, e la sua ricostruzione sarà ordinata e plausibile in un modo in cui la sessione vera non lo era mai stata. La plausibilità è precisamente il rischio.

**Il formato non è un contratto.** `.jsonl`, i nomi dei campi, la posizione delle cartelle: sono dettagli interni che possono cambiare fra due versioni senza preavviso. Se costruite qualcosa di automatico su queste strutture, mettete in conto di ripararlo.

## Fatelo una volta quando non serve

Il momento peggiore per imparare questa procedura è quando vi serve, cioè con i crediti finiti e il lavoro a metà.

Prendete una sessione lunga che avete già chiuso, di cui ricordate il finale. Chiedete a una sessione nuova di trovarla, leggerne gli ultimi messaggi e riassumervela. Poi confrontate il riassunto con quello che ricordate: quello che manca è la misura di quanto vi dovrete fidare la prossima volta. Sono dieci minuti, e la prossima volta li fate in due.

Se lo provate, [scrivetemi com'è andata](mailto:vincenzoml@gmail.com?subject=Handover%20fra%20sessioni&body=Da%20quale%20applicazione%20a%20quale%3A%20%0ACosa%20ha%20ritrovato%3A%20%0ACosa%20ha%20perso%3A%20). Mi interessa soprattutto la seconda parte.

## Il lavoro resta vostro se resta leggibile

Al fondo c'è una cosa più semplice di un trucco per risparmiare crediti: una conversazione di tre ore con un agente è un documento di lavoro. Finché resta un file di testo sul vostro disco potete ritrovarlo, cercarlo dentro, passarlo a un altro strumento e rileggerlo fra un anno.

Sono le stesse tre ore. Cambia solo che qualcuno le ha scritte da qualche parte, e che voi sapete dove.

## Fonti e approfondimenti

- Il mio articolo [Ho chiesto all'agente di coding di spendere meno token](#/post/quiet-mode-agenti-coding), da cui viene la regola di filtrare gli output invece di ingoiarli.
- Anthropic, [How Claude remembers your project](https://docs.anthropic.com/en/docs/claude-code/memory), sui file di istruzioni persistenti e sulla loro gerarchia.
- Anthropic, [Effective context engineering for AI agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents), su recupero progressivo e contesto ad alto segnale.
- Anthropic, [Code execution with MCP](https://www.anthropic.com/engineering/code-execution-with-mcp), esempio quantitativo di quanto costa far passare tutto dal contesto.
- Liu et al., [Lost in the Middle](https://arxiv.org/abs/2307.03172), sul perché un contesto pieno non equivale a un contesto usato: l'informazione al centro viene sfruttata peggio di quella agli estremi.
