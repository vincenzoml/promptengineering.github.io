---
title: Un modello non sa che ore sono
description: Non ha orologio, non ha finestre, e la sua conoscenza del mondo si ferma a una data. Cosa questo comporta davvero nel lavoro quotidiano, e le tre abitudini che lo rendono un non problema.
date: 2026-05-26
author: vincenzo
tags: [limiti, contesto, metodo, LLM]
image: /images/posts/cover-sa-che-ore-sono.png
lang: it
---

![Un modello non sa che ore sono](/images/posts/cover-sa-che-ore-sono.png)

Dove finisce la conoscenza di un modello e perché la data conta più di quanto sembri; il caso subdolo in cui vi risponde con sicurezza su una norma cambiata da un anno; e come si rimedia in una riga, prima di accorgersi del problema invece che dopo.

Chiedete a un modello che giorno è. Alcuni ve lo dicono, perché il servizio che li ospita glielo ha scritto in cima alla conversazione, dove voi non vedete. Altri tirano a indovinare, e sbagliano. Nessuno lo *sa*: non c'è un orologio là dentro, e non c'è una finestra da cui guardare fuori.

Detto così sembra una curiosità. È invece il capofila di una famiglia di errori che in uno studio professionale costano tempo vero.

## Due cose diverse che si confondono

C'è la data di oggi, e c'è il limite della conoscenza. Sono problemi distinti.

La **data di oggi** è banale da risolvere: basta dirgliela, e molti servizi lo fanno già per conto vostro. Se il vostro strumento non lo fa, e state chiedendo qualcosa che dipende dal calendario — "quanti giorni mancano alla scadenza", "il termine cade in un festivo" — scrivergli la data è un secondo di lavoro che elimina un'intera classe di errori.

Il **limite della conoscenza** è più serio. Un modello ha imparato da testi raccolti fino a un certo punto nel tempo, e da lì in poi non sa niente. Non "sa di non sapere": semplicemente il mondo, per lui, si ferma lì. Se una norma è cambiata dopo, o se un prodotto è uscito dopo, il modello vi risponderà con la versione che conosce, e la esporrà con la stessa sicurezza di sempre.

Il caso peggiore non è quando ignora del tutto una cosa — lì di solito lo dice. È quando la cosa esisteva già, ma è cambiata: allora ha una risposta, ed è quella vecchia.

## Perché la sicurezza inganna

Chi lavora con questi sistemi impara presto che il tono non è un indicatore di affidabilità. Sulle date la cosa è particolarmente insidiosa, perché una risposta obsoleta è indistinguibile da una attuale: stessa prosa, stessa precisione, stessi riferimenti.

Un commercialista, in aula, ha chiesto di riassumere gli obblighi di una certa comunicazione. Il riassunto era perfetto — per l'anno precedente. Nessun segnale, nessuna esitazione. Se ne è accorto perché conosceva la materia; un collaboratore giovane non se ne sarebbe accorto, e avrebbe avuto in mano un documento sbagliato scritto benissimo.

Questo è il punto pratico: il rischio non è distribuito a caso, si concentra su chi ha meno strumenti per riconoscerlo.

## Le tre abitudini

**Dategli la data e il contesto temporale.** Quando la risposta dipende dal quando, mettetelo nella richiesta: "oggi è il 12 marzo 2026", "normativa vigente a oggi", "il contratto è del 2019". Costa una riga e vale più di qualsiasi verifica successiva, perché sposta il modello nel tempo giusto invece di lasciarlo dove sta.

**Sulla materia che cambia, dategli il testo.** Se lavorate su qualcosa di normato, non chiedete al modello cosa dice la norma: incollategli la norma e chiedetegli di applicarla. È la differenza fra usarlo come enciclopedia — mestiere in cui è mediocre e pericoloso — e usarlo come lettore, che è il mestiere in cui è eccellente. Vale identico per le circolari, i regolamenti interni, i capitolati.

**Chiedete la data della conoscenza.** "Fino a quando arrivano le tue informazioni su questo argomento?" è una domanda a cui i modelli rispondono in modo ragionevolmente onesto, ed è utile prima di fidarsi di qualcosa che potrebbe essere cambiato. Non è una garanzia — anche quella risposta è una stima — ma è meglio del silenzio.

## Il rovescio

Vale la pena notare che gli strumenti che cercano in rete risolvono metà del problema e ne aprono un altro: le informazioni sono aggiornate, ma provengono da qualunque cosa il motore abbia trovato, e la qualità della fonte diventa un vostro problema. Un modello che cita una pagina qualsiasi è meno affidabile di un modello che ragiona su un testo che gli avete dato voi, sapendo cos'è.

## Modello, prodotto e strumenti

La frase del titolo vale per il modello isolato. Il prodotto può aggiungere un system prompt con data corrente; un agente può chiamare un orologio, un calendario o una ricerca web. Quando Claude o ChatGPT risponde correttamente, bisogna chiedersi da quale strato arriva l'informazione.

La distinzione evita test sbagliati. Se chiediamo «che ore sono?» stiamo valutando integrazione e permessi del prodotto, non conoscenza appresa nei pesi. Se chiediamo «qual è la versione corrente di una libreria?» serve una fonte aggiornata, non la data del system prompt.

## Quattro tempi diversi

1. **data della conversazione**, fornita dal sistema;
2. **cutoff della conoscenza**, fino a cui arriva il training dichiarato;
3. **data della fonte**, quando la pagina o il documento è stato aggiornato;
4. **validità del fatto**, l'intervallo in cui prezzo, norma o incarico è vero.

Una pagina aggiornata oggi può descrivere dati del 2023. Un PDF del 2020 può contenere una definizione ancora vigente. «Fonte recente» e «fatto corrente» non sono sinonimi.

## Rendere esplicita la data di validità

Per le richieste instabili uso una formula precisa:

```text
Verifica questa informazione alla data del 9 agosto 2026.
Usa fonti primarie. Per ogni fatto variabile indica data della fonte e
data a cui il fatto si riferisce. Se non puoi verificare, non completare
con la tua memoria: marca "non verificato".
```

Per leggi e policy aggiungo giurisdizione e versione. Per prezzi, valuta, imposte e regione. Per software, numero di release e canale. Per persone, ruolo e data di osservazione.

## La ricerca web non è una macchina della verità

Un motore ottimizza reperibilità, non autorità. Pagine SEO possono superare documentazione ufficiale; snippet possono omettere negazioni; articoli nuovi possono ricopiare una fonte vecchia. L'agente deve aprire il documento e collegare ogni affermazione al passaggio pertinente.

Ordine preferibile:

1. norma, documentazione o comunicato primario;
2. dataset e paper originale;
3. fonte secondaria autorevole per contesto;
4. aggregatori soltanto per scoprire fonti.

Se le fonti primarie divergono, mostrate versioni e date invece di fonderle.

## Procedure sensibili al tempo

I workflow automatici devono portare timestamp e scadenza. Una verifica KYC, una quotazione o una disponibilità GPU non rimane valida indefinitamente. Inserite un TTL: se il dato è troppo vecchio, il sistema lo recupera di nuovo o si ferma.

Anche i test vanno rieseguiti dopo aggiornamenti del modello. Un prompt che produceva correttamente JSON o citazioni può cambiare comportamento pur mantenendo lo stesso nome commerciale.

## Un audit di freschezza

Per un articolo o una decisione, estraete tutte le affermazioni che possono cambiare: prezzi, ruoli, versioni, numeri, policy, disponibilità, prestazioni. Per ciascuna annotate fonte primaria, data di controllo e prossima revisione. Il resto — definizioni storiche, teoremi, descrizioni stabili — non richiede la stessa manutenzione.

Questo trasforma «aggiornato» da aggettivo a proprietà verificabile.

## Dateglielo, non speratelo

La regola che ne ricavo, dopo un paio d'anni di uso quotidiano: **il modello è bravissimo a lavorare sui documenti, e inaffidabile a ricordarseli**. Tutto quello che conta, dateglielo. Quello che non gli date, non lo state usando: lo state solo sperando.

## Fonti e approfondimenti

- OpenAI, [Web search tool](https://platform.openai.com/docs/guides/tools-web-search), documentazione su ricerca e citazioni.
- Anthropic, [Web search tool](https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/web-search-tool), documentazione ufficiale.
- OpenAI, [Model release notes](https://help.openai.com/en/articles/9624314-model-release-notes), cronologia dei cambiamenti.
- Anthropic, [Model deprecations](https://docs.anthropic.com/en/docs/about-claude/model-deprecations), ciclo di vita dei modelli.
