---
title: Ho chiesto all'agente di coding di spendere meno token. Ha funzionato
description: Il mio prompt preferito chiede all'agente di usare la propria intelligenza per risparmiare token, lavorare in silenzio e interrompermi soltanto quando una decisione comporta un rischio. Ecco che cosa cambia davvero.
date: 2026-08-25
author: vincenzo
tags: [agenti, Claude Code, token, contesto, metodo]
image: /images/posts/cover-quiet-mode-agenti-coding.png
lang: it
---

![Ho chiesto all'agente di spendere meno token](/images/posts/cover-quiet-mode-agenti-coding.png)

C'è un momento riconoscibile nelle sessioni lunghe con un agente di coding. La richiesta iniziale è circoscritta; l'agente esplora il repository, apre file vicini, cerca simboli, esegue test. Poi comincia il diario: che cosa sta per fare, che cosa ha appena fatto, che cosa «sembra» aver trovato. Un comando restituisce cinquecento righe. Un altro ripete quasi le stesse. Quando arriva la modifica, il contesto contiene più cronaca che problema.

La diagnosi è ormai comune. Si consigliano server MCP specializzati, hook, indici semantici, compattatori, wrapper per la shell e sistemi di memoria. Sono strumenti utili. Io ho cominciato con una frase:

> Usa la tua intelligenza per risparmiare crediti.

Oggi la metto quasi sempre nelle istruzioni, anche quando uso un setup che non ho configurato io. È deliberatamente meno precisa del resto del prompt: affida al modello l'obiettivo e gli lascia scegliere dove evitare sprechi. Un agente capace può decidere di cercare prima di aprire, leggere un estratto invece di un file intero, riusare un risultato, smettere di raccontare passaggi ovvi. Con modelli migliori la frase tende a diventare più utile, perché aumenta il numero di decisioni che possono prendere bene da soli. Confini, eccezioni e verifiche, nelle righe successive, proteggono la qualità.

Questo è il prompt, nella versione che uso:

```text
Use your intelligence to hyperoptimize saving AI tokens and credits while you work.

Operate in quiet mode. Do not narrate your work or explain routine steps.
Minimize token usage aggressively.

Only respond during the task if:
1. You are about to make a high-risk decision involving files, code,
   data loss, artifacts, or irreversible changes — ask for permission.
2. You make a moderately risky assumption — state it briefly.

Otherwise, stay silent until completion. At the end, provide only a
1–2 line summary, unless I ask for details.

Never paste raw shell command output directly into chat or source it
into your context. Redirect all output to files, check file sizes first,
and read only the relevant excerpts.
```

Tutto qui. La finestra di contesto rimane quella. L'agente, però, riceve un criterio economico con cui scegliere mentre lavora.

## Tre consumi che vengono confusi

Dire «risparmio token» senza specificare quali rende qualsiasi percentuale sospetta. In una sessione agentica almeno tre flussi sono diversi:

1. **output visibile del modello**: piani, aggiornamenti, spiegazioni, riepilogo;
2. **risultati degli strumenti reimmessi nel contesto**: file letti, log, diff, risposte di API;
3. **contesto di input dei turni successivi**: istruzioni, cronologia, tool call e risultati che il modello deve rileggere.

Il silenzio riduce direttamente il primo. La regola sugli output riduce il secondo. Entrambi, se la piattaforma conserva la cronologia, riducono anche il terzo nei turni seguenti.

Non riducono necessariamente il ragionamento interno del modello. Non rendono gratuiti i tool. Non impediscono alla piattaforma di reinviare istruzioni fisse o definizioni degli strumenti. E non garantiscono una bolletta inferiore nello stesso rapporto: caching, prezzi differenziati, compattazione e implementazione dell'agente cambiano il conto.

Questa distinzione spiega perché il prompt funziona senza attribuirgli poteri mistici.

## Il vero costo sono gli output non filtrati

La riga che, nella pratica, mi fa risparmiare di più è questa:

> Redirect all output to files, check file sizes first, and read only the relevant excerpts.

Un agente può lanciare un test e ricevere migliaia di righe, aprire un bundle minificato, stampare un JSON enorme o incollare l'intero risultato di una ricerca. Anche se la risposta all'utente è di due righe, quel materiale può essere già entrato nel contesto.

La strategia corretta assomiglia al modo in cui un ingegnere usa una console:

- eseguire il comando salvando l'output;
- controllare stato di uscita e dimensione;
- cercare errori, nomi o pattern specifici;
- leggere poche righe attorno ai punti rilevanti;
- allargare l'ispezione solo se l'evidenza lo richiede.

[Anthropic ha misurato lo stesso problema su scala MCP](https://www.anthropic.com/engineering/code-execution-with-mcp). Quando il modello chiama direttamente molti strumenti, si porta dietro definizioni e risultati che spesso servono solo per un passaggio intermedio. Nel loro esempio, facendo eseguire orchestrazione e filtri in un ambiente di codice, il contesto è sceso da circa 150.000 token a circa 2.000. Quel 98,7% appartiene al loro esperimento, non al mio prompt. Lo cito perché rende visibile una cosa facile da sottovalutare: il costo dipende anche da come facciamo arrivare gli strumenti al modello.

## Perché la narrazione prolifera

Gli assistenti sono progettati per essere leggibili, rassicuranti e collaborativi. «Ora ispeziono il repository» comunica attività. «Ho individuato il problema» mantiene l'utente orientato. In un compito breve è un costo minimo e può aumentare la fiducia.

In una sessione di sviluppo articolata, la stessa convenzione si ripete decine di volte. Il messaggio descrive spesso un'azione già rappresentata dalla tool call. Diventa duplicazione.

Senza una politica di interruzione, la buona educazione diventa telecronaca. Nel mio prompt la frequenza dei messaggi dipende dal rischio:

- un'azione reversibile e ordinaria procede in silenzio;
- un'ipotesi che può cambiare il risultato viene dichiarata;
- un'operazione distruttiva o difficilmente recuperabile richiede permesso;
- il completamento produce un riepilogo minimo.

Questa politica conserva i messaggi che cambiano una decisione. Elimina quelli che attestano soltanto che l'agente è ancora vivo.

## Dove il quiet mode può fare danni

Quiet mode può anche peggiorare il lavoro. Su un task ambiguo, vedere una scaletta iniziale permette di correggere la direzione prima che l'agente tocchi venti file. Durante un incidente operativo, gli aggiornamenti servono a coordinare persone. In un lavoro esplorativo, il percorso può essere parte del risultato.

Esistono poi due failure mode meno evidenti.

Il primo è l'**assunzione muta**. Per non interrompere, il modello prende una decisione che cambia l'architettura o interpreta un requisito in modo conveniente. La seconda eccezione del prompt esiste per questo: un'ipotesi moderatamente rischiosa va resa esplicita, anche se non richiede ancora autorizzazione.

Il secondo è la **compressione della verifica**. «Sii breve» può diventare «fai meno controlli» se il criterio non distingue comunicazione e lavoro. Per questo chiedo di minimizzare i token, non le verifiche; e alla fine giudico artefatti, test e diff, non la sicurezza del riepilogo.

Per attività ad alto rischio aggiungo checkpoint espliciti: piano prima delle modifiche, consenso prima di migrazioni o cancellazioni, rapporto di verifica con evidenze. Quiet mode è una policy di comunicazione, non una deroga al processo.

## Il mio risultato, e il limite della testimonianza

Nelle mie sessioni — repository grandi, Git, test, debugging, connessioni SSH — molti task complessi rimangono sotto i mille token di risposta visibile per richiesta. Prima erano facilmente dominati da aggiornamenti e log. È un'osservazione personale, non un benchmark: cambiano modello, piattaforma, caching, difficoltà e quantità di output degli strumenti.

La versione precedente di questo articolo trattava quell'osservazione quasi come una misura sufficiente. Non lo è. Per sapere se il prompt risparmia davvero bisogna misurare insieme costo e qualità.

## Provatelo su un lavoro vero

Prendete cinque task simili. Eseguitene alcuni con le istruzioni abituali e gli altri aggiungendo quiet mode. Tenete fissi modello e repository; confrontate token, costo, test superati e tempo di revisione. Se risparmia soltanto perché controlla meno, ha fallito.

Se fate la prova, [scrivetemi due righe](mailto:vincenzoml@gmail.com?subject=Quiet%20mode%3A%20il%20mio%20risultato&body=Task%3A%20%0AModello%20e%20strumento%3A%20%0APrima%2Fdopo%3A%20%0ACosa%20%C3%A8%20migliorato%20o%20peggiorato%3A%20) oppure [mandatemi un messaggio su LinkedIn](https://www.linkedin.com/in/vincenzo-ciancia-2032445/). Mi bastano task, modello, prima/dopo e una cosa che è peggiorata. Questo sito è statico e voglio lasciarlo tale: niente account, database o moderazione automatica. Con il permesso di chi scrive raccoglierò qui i risultati interessanti, comprese le smentite. È più vicino a una corrispondenza fra persone che a una colonna di commenti, e probabilmente produce dati migliori.

## Una versione adattata ai diversi lavori

Il prompt base è severo. Si può modularlo.

Per manutenzione ordinaria:

```text
Quiet mode. Nessuna narrazione delle azioni reversibili.
Interrompimi solo per rischio, assunzioni che cambiano il risultato o blocchi.
Filtra gli output degli strumenti prima di inserirli nel contesto.
Alla fine: file cambiati, verifiche eseguite, questioni residue. Massimo 5 righe.
```

Per refactoring architetturale:

```text
Mostra prima un piano con invarianti, confini e strategia di rollback.
Dopo l'approvazione lavora in quiet mode.
Fermati se il diff supera il perimetro concordato o se un test rivela
un comportamento non documentato.
```

Per ricerca e diagnosi:

```text
Non narrarmi ogni comando. Mantieni un diario di evidenze in un file.
Aggiornami quando cambia l'ipotesi principale o servono nuovi dati.
Alla fine separa: fatti osservati, inferenze, ipotesi scartate, prossimo test.
```

Il principio resta stabile: frequenza e dettaglio della comunicazione devono seguire rischio e bisogno decisionale, non l'impulso dell'assistente a descriversi.

## Perché continuo a usarlo

Il prompt assegna all'agente un criterio di spesa e gli mette attorno poche regole:

- il contesto è una risorsa finita;
- gli output voluminosi vengono filtrati vicino alla sorgente;
- il lavoro ordinario non richiede telecronaca;
- le eccezioni dipendono dal rischio;
- la qualità viene verificata fuori dalla prosa dell'agente.

Un indice semantico può far risparmiare ancora più contesto. Un server MCP ben progettato può restituire strutture più piccole. La compattazione può allungare la sessione. Quiet mode viene prima: impedisce di spendere token su materiale che nessuno userà.

I token non sono soltanto una voce di prezzo. Sono lo spazio attentivo dell'agente. Riempirlo con frasi rituali e terminali interi significa chiedergli di ritrovare il problema dentro il resoconto del problema.

«Usa la tua intelligenza per risparmiare crediti» è la riga che ormai porto da un setup all'altro. Più il modello sa pianificare, cercare e usare strumenti, più occasioni trova per applicarla. Poi quiet mode toglie la telecronaca; le regole sul rischio gli dicono quando deve tornare a parlare. La frase breve indica la direzione. Il resto impedisce che, per risparmiare, imbocchi una scorciatoia stupida.

## Fonti e approfondimenti

- Anthropic, [Effective context engineering for AI agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents), su *context rot*, recupero progressivo e contesto ad alto segnale.
- Anthropic, [Code execution with MCP](https://www.anthropic.com/engineering/code-execution-with-mcp), esempio quantitativo di filtraggio e orchestrazione fuori dal contesto.
- Anthropic, [Advanced tool use](https://www.anthropic.com/engineering/advanced-tool-use), ricerca dinamica e uso efficiente degli strumenti.
- Anthropic, [Claude API pricing](https://docs.anthropic.com/en/docs/about-claude/pricing), su token di input/output e contenuto restituito dagli strumenti.
- Liu et al., [Lost in the Middle](https://arxiv.org/abs/2307.03172), sul degrado nell'uso di informazione dentro contesti lunghi.
- Il mio articolo originale su Medium, [Forget Caveman. I Told Claude to Spend Fewer Tokens. And It Worked.](https://medium.com/@vincenzoml/forget-caveman-i-told-claude-to-spend-fewer-tokens-and-it-worked-0c2270cd11d9), da cui nasce questa versione corretta e ampliata.
