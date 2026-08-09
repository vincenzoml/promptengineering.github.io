---
title: L'arte del prompt engineering — guida pratica
description: Un prompt efficace non è una formula magica ma una specifica verificabile. Come dare contesto, esempi e criteri di qualità, scegliere gli strumenti e costruire un ciclo di lavoro che regga anche fuori dalle demo.
date: 2026-01-06
author: vincenzo
tags: [guida, fondamenti, AI]
image: /images/posts/cover-welcome.png
lang: it
---

Il prompt engineering ha avuto una fase astrologica. Liste di verbi potenti, acronimi da ricordare, formule da copiare e incollare. «Agisci come il massimo esperto mondiale» sembrava capace di trasformare una domanda vaga in un lavoro professionale.

Non funziona così. Un modello linguistico non diventa competente perché lo investiamo di un titolo. Può però lavorare molto meglio quando gli rendiamo visibili le parti del problema che noi abbiamo in testa e lui no: destinatario, materiale disponibile, vincoli, risultato atteso e modo in cui giudicheremo quel risultato.

Questa è la definizione operativa che uso:

> Un prompt è una specifica temporanea per un sistema probabilistico.

«Specifica» perché descrive un lavoro. «Temporanea» perché vale dentro un contesto che cambia. «Probabilistico» perché una buona richiesta aumenta la probabilità di un buon risultato, non lo garantisce.

Il resto viene da qui.

## Prima del prompt: decidere che lavoro stiamo affidando

La richiesta «scrivi una relazione sull'intelligenza artificiale» contiene quasi zero informazione utile. Potrebbe essere una nota per il consiglio di amministrazione, un capitolo scolastico, una rassegna scientifica o una pagina commerciale. Il modello colma i vuoti scegliendo la versione statisticamente più comune. È così che si ottiene un testo corretto, levigato e intercambiabile con mille altri.

Prima di scrivere, conviene rispondere a cinque domande:

1. **Chi userà il risultato?** Un collega tecnico, un cliente, un giudice e uno studente hanno bisogni diversi.
2. **Che decisione deve rendere possibile?** Informare non è abbastanza: scegliere un fornitore, capire un rischio, approvare una spesa, imparare una procedura.
3. **Su quali materiali deve basarsi?** Documenti forniti, fonti da cercare, dati interni, oppure sola conoscenza del modello.
4. **Quali errori costano di più?** Un numero inventato, una citazione falsa, un tono inappropriato, una procedura incompleta.
5. **Che forma deve avere?** Lunghezza, struttura, lingua, formato e livello di dettaglio.

Se non sappiamo rispondere, il problema non è ancora pronto per essere delegato. Possiamo comunque usare il modello per formularlo: «Fammi le domande necessarie per trasformare questa idea in un incarico eseguibile». È uno degli usi più sensati dell'AI: non produrre subito, ma rendere esplicito il lavoro.

## La struttura minima che regge

Per molte attività bastano sei blocchi. Non servono etichette rituali; servono le informazioni.

```text
Obiettivo
Prepara una nota che consenta al direttore di scegliere fra A e B.

Destinatario
Conosce il settore, non l'implementazione tecnica. Ha dieci minuti.

Materiale
Usa i tre documenti allegati. Se cerchi sul web, cita solo fonti primarie
e indica la data a cui si riferiscono prezzi e funzionalità.

Vincoli
Non inventare dati mancanti. Se due fonti divergono, mostra la divergenza.
Separa fatti, inferenze e raccomandazioni.

Consegna
Sintesi di 120 parole; tabella di confronto; rischi; raccomandazione motivata.

Criteri di qualità
Ogni numero deve essere verificabile. La raccomandazione deve cambiare
esplicitamente se cambia una delle tre ipotesi principali.
```

Il blocco più trascurato è l'ultimo. Dire al modello cosa produrre non equivale a dirgli cosa rende il prodotto buono. «Scrivi un articolo professionale» descrive un'impressione. «Apri con il problema concreto, definisci i termini al primo uso, attribuisci ogni dato variabile a una fonte con data, includi un controesempio e chiudi con una procedura verificabile» descrive caratteristiche osservabili.

## Il contesto giusto non è il contesto massimo

Caricare tutto è allettante: cartelle intere, chat precedenti, decine di pagine «nel dubbio». Ma il contesto è una risorsa finita e l'informazione pertinente può essere sepolta da quella accessoria. Il fenomeno è stato misurato: nei compiti su documenti lunghi, le prestazioni possono peggiorare quando l'informazione importante si trova nel mezzo del contesto, il cosiddetto *lost in the middle*.

Il criterio utile è il rapporto segnale/rumore. Fornite:

- i documenti che contengono i fatti necessari;
- una breve spiegazione del perché contano;
- la versione corrente del lavoro, non tutte le versioni storiche;
- esempi rappresentativi, non un archivio indifferenziato.

Per attività lunghe, tenete fuori dalla conversazione una piccola «fonte di verità»: obiettivi, decisioni prese, termini definiti, file coinvolti, questioni aperte. I sistemi agentici moderni usano lo stesso principio con compattazione, memoria esterna e recupero progressivo. Anthropic lo descrive come ricerca del più piccolo insieme di token ad alto segnale capace di produrre l'esito desiderato.

## Gli esempi insegnano più degli aggettivi

«Usa un tono brillante» è ambiguo. Un paragrafo scritto da voi è un dato. Due esempi, scelti bene, mostrano ritmo, densità, rapporto con il lettore e livello di tecnicità.

Gli esempi devono essere pertinenti al compito. Una buona email non insegna automaticamente a scrivere un saggio; un articolo divulgativo non definisce il tono di una contestazione legale. Conviene accompagnarli con poche annotazioni:

```text
Nel primo esempio conserva le frasi brevi e l'apertura concreta.
Nel secondo conserva il modo in cui distinguo fatti e opinioni.
Non imitare le battute né ripetere le metafore.
```

Questa pratica è una forma leggera di *few-shot prompting*: invece di definire solo a parole il comportamento, lo mostriamo. Le guide ufficiali di OpenAI e Anthropic raccomandano entrambe esempi pertinenti e istruzioni chiare; non perché esista un formato sacro, ma perché riducono le interpretazioni possibili.

## Dividere il lavoro nei punti in cui può essere verificato

Un prompt enorme che chiede ricerca, analisi, scrittura, fact-checking e impaginazione in un colpo solo produce un oggetto difficile da controllare. Quando l'errore appare nell'ultima pagina non sappiamo in quale fase sia nato.

La divisione più robusta segue le verifiche:

1. definire domanda, destinatario e criteri;
2. raccogliere le fonti e annotare cosa sostiene ciascuna;
3. costruire una scaletta con tesi e controtesi;
4. scrivere una sezione alla volta;
5. controllare affermazioni, numeri e citazioni;
6. fare una revisione editoriale separata;
7. verificare il formato finale.

Non è una catena rigida. Se una fonte smentisce l'ipotesi, si torna alla scaletta. Se una sezione non sostiene la decisione, si elimina. Il vantaggio è avere artefatti intermedi ispezionabili.

Per il codice vale lo stesso principio: riprodurre il difetto, localizzare la causa, cambiare il minimo necessario, eseguire i test pertinenti, poi quelli più ampi. «Sistema il progetto» lascia troppe decisioni implicite e incoraggia esplorazioni costose.

## Ricerca e generazione sono lavori diversi

Il modello può scrivere una frase plausibile anche quando non possiede il fatto. La fluidità non porta con sé una garanzia di provenienza. Per tutto ciò che cambia — prezzi, leggi, versioni software, incarichi, benchmark, disponibilità di prodotti — occorre consultare fonti aggiornate.

Una procedura semplice:

- chiedere prima una tabella di affermazioni e fonti;
- preferire documentazione ufficiale, atti normativi e articoli scientifici originali;
- aprire davvero le fonti, non fidarsi del titolo o del riassunto del motore di ricerca;
- riportare la data di osservazione per i dati instabili;
- segnalare ciò che rimane inferenza.

La citazione non è decorazione. Deve permettere al lettore di controllare la frase a cui è attaccata. Dieci link raccolti in fondo, senza corrispondenza con le affermazioni, danno autorità grafica e poca verificabilità.

## Chiedere critica, non approvazione

I modelli sono addestrati anche a essere utili e gradevoli. Se chiediamo «va bene?», spesso riceviamo una rassicurazione. Una revisione seria assegna un ruolo avversario e criteri concreti:

```text
Non riscrivere ancora.
Elenca le cinque debolezze che potrebbero far respingere questo testo.
Per ciascuna indica: passaggio esatto, criterio violato, gravità,
prova necessaria e correzione minima.
Se non trovi una prova, scrivi "non verificato".
```

Poi conviene separare la diagnosi dalla correzione. Se il modello critica e riscrive nello stesso gesto, può coprire il problema senza mostrarlo. Studi come *Self-Refine* hanno mostrato che cicli di feedback e revisione possono migliorare diversi compiti; non sono però una certificazione automatica. Un modello può anche razionalizzare il proprio errore o ottimizzare un criterio mal definito.

## Prompt, strumenti e responsabilità

Un buon prompt non sostituisce uno strumento adatto. Per sommare mille righe usate un programma o un foglio di calcolo. Per sapere se una norma è vigente consultate la fonte normativa. Per modificare un repository fate eseguire test e controllate la differenza. Il modello serve a collegare intenzione, materiale e strumenti; non deve simulare tutti gli strumenti in prosa.

La responsabilità resta umana in modo molto concreto: qualcuno decide quali fonti sono ammissibili, quale margine di errore è accettabile e chi firma il risultato. Nei lavori ad alto impatto, «lo ha detto l'AI» non è né una fonte né una procedura.

## Un prompt riutilizzabile, senza superstizione

Questo schema copre gran parte del lavoro professionale:

```text
Devo ottenere: [risultato e decisione che deve supportare].
Lo userà: [destinatario, conoscenze, tempo disponibile].
Lavora su: [materiali e fonti ammesse].

Prima di produrre il risultato:
1. segnala le informazioni indispensabili che mancano;
2. esplicita le ipotesi che influenzano la conclusione;
3. proponi una struttura breve e verificabile.

Vincoli: [accuratezza, esclusioni, tono, formato, lunghezza].
Criteri: [condizioni osservabili di qualità].

Durante il lavoro distingui fatti, inferenze e proposte.
Non inventare fonti o dati. Alla fine esegui un controllo contro i criteri
e segnala ciò che richiede verifica umana.
```

Va adattato, non venerato. Per un compito semplice può ridursi a due righe; per una due diligence richiede materiali, responsabilità e passaggi molto più precisi. Il prompt migliore è quello che rende visibili le decisioni necessarie senza aggiungere cerimonia.

## La regola che rimane

Prompt engineering non significa trovare la frase che «sblocca» il modello. Significa progettare l'interazione in modo che il lavoro sia osservabile, correggibile e proporzionato al rischio.

Quando una risposta è mediocre, prima di cambiare aggettivi controllate quattro cose: il modello sa per chi sta lavorando? Ha le fonti necessarie? Conosce i criteri? Può usare lo strumento giusto e mostrare come ha verificato?

Quasi sempre il salto di qualità è lì.

## Fonti e approfondimenti

- Anthropic, [Effective context engineering for AI agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents), su contesto ad alto segnale, recupero progressivo e compattazione.
- OpenAI, [Prompt engineering](https://platform.openai.com/docs/guides/prompt-engineering), guida ufficiale a istruzioni, esempi e contesto.
- Anthropic, [Prompt engineering overview](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview), documentazione ufficiale.
- Liu et al., [Lost in the Middle: How Language Models Use Long Contexts](https://arxiv.org/abs/2307.03172), analisi della posizione dell'informazione nei contesti lunghi.
- Madaan et al., [Self-Refine: Iterative Refinement with Self-Feedback](https://arxiv.org/abs/2303.17651), risultati e limiti di un ciclo di autocritica.
- Gao et al., [PAL: Program-aided Language Models](https://arxiv.org/abs/2211.10435), sull'uso di interpreti esterni per il calcolo.
