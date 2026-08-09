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

La regola che ne ricavo, dopo un paio d'anni di uso quotidiano: **il modello è bravissimo a lavorare sui documenti, e inaffidabile a ricordarseli**. Tutto quello che conta, dateglielo. Quello che non gli date, non lo state usando: lo state solo sperando.
