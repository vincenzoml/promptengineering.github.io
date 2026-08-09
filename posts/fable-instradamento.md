---
title: Perché a metà lavoro vi risponde un altro modello
description: Claude Fable 5 controlla ogni richiesta e su certi argomenti la passa a un altro modello, con tanto di avviso. Non è un guasto, è documentato, e può scattare perfino alla prima riga — per colpa di una cartella che si chiama male.
date: 2026-08-11
author: vincenzo
tags: [Fable, limiti, strumenti, metodo]
image: /images/posts/cover-fable-instradamento.png
lang: it
---

![Perché a metà lavoro vi risponde un altro modello](/images/posts/cover-fable-instradamento.png)

Le quattro famiglie di argomenti che fanno cambiare modello, dove finisce la richiesta quando accade, e perché tocca proprio i mestieri che di quegli argomenti vivono. Il caso che sembra un guasto e non lo è, con il rimedio più banale che ci sia. E cosa racconta, questo meccanismo, degli strumenti che useremo fra due anni.

Succede così: state lavorando, fate una domanda come le cento precedenti, e insieme alla risposta compare un avviso — il modello è cambiato. Da lì in avanti risponde un altro, e il selettore resta su quello. Non avete chiesto niente di strano, nessuno vi ha bloccato, e la risposta che ricevete è perfettamente normale. Solo che l'ha scritta qualcun altro.

È un comportamento documentato di **Claude Fable 5**, il modello veloce di Anthropic, ed è interessante due volte: come istruzione d'uso per chi ci lavora, e come finestra su come i fornitori gestiscono i modelli più capaci. Cominciamo dall'istruzione d'uso.

## Come funziona

Fable esegue controlli automatici — dei classificatori — su ogni richiesta che riceve. Quando uno di questi riconosce un argomento fuori dal perimetro assegnato al modello, la richiesta non viene rifiutata: viene **passata a un altro modello**, che risponde al suo posto. Voi vedete un avviso, la risposta arriva con l'indicazione di chi l'ha scritta, e la conversazione prosegue — sull'altro modello, fino alla fine. Il ritorno automatico non c'è.

Le famiglie di controllo dichiarate nella documentazione sono quattro:

- **sicurezza informatica offensiva** — costruzione di exploit, malware, strumenti d'attacco;
- **biologia e chimica a doppio uso** — virologia, tossicologia, progettazione di farmaci e molecole;
- **estrazione del ragionamento** — tentativi di far emergere il processo interno del modello;
- **sviluppo di modelli di frontiera** — infrastrutture di addestramento distribuito, acceleratori, kernel specializzati.

Le destinazioni cambiano con la materia: le richieste di area biologica e chimica ripartono su Opus 5, quelle di sicurezza offensiva su Opus 4.8. Sulla sicurezza, l'azienda stessa avverte di aspettarsi passaggi frequenti — non è un'eventualità rara che capita agli sfortunati, è il funzionamento previsto.

Il motivo dichiarato è onesto e vale la pena riportarlo com'è: capacità avanzate in quei campi, nelle mani sbagliate, servono a costruire attacchi informatici su larga scala o armi biologiche. Fable è veloce ed economico, cioè adatto all'automazione di massa — ed è esattamente il profilo che un fornitore non vuole offrire, a basso costo, su quelle materie. I modelli di riserva rispondono alle stesse domande, ma con caratteristiche diverse e su un percorso più sorvegliato.

## Perché tocca chi non c'entra niente

Il controllo lavora per somiglianza, non per comprensione — è la stessa architettura dei rifiuti, di cui [abbiamo già scritto](#/post/quando-il-modello-dice-no), applicata all'instradamento. Riconosce la *forma* di una richiesta pericolosa. E la forma, purtroppo, la condividono molti lavori rispettabilissimi.

Chi scrive la documentazione di un dispositivo medico parla di meccanismi biologici con proprietà di linguaggio. Chi prepara una lezione di biochimica pure. Un consulente che redige la parte tecnica di una perizia tossicologica sta producendo, parola per parola, il tipo di testo che il classificatore sorveglia. E chi fa sicurezza informatica *difensiva* — che è un mestiere enorme e in crescita — passa le giornate a descrivere attacchi, perché non c'è altro modo di difendersi da qualcosa che descriverlo. Nessuno di loro chiede nulla di illecito; tutti frequentano il vocabolario sbagliato.

Per loro il falso positivo non è un incidente occasionale: è il rumore di fondo del mestiere. E conviene saperlo prima, perché la prima volta che succede su una consegna urgente, il sospetto di "aver combinato qualcosa" fa perdere più tempo del passaggio stesso.

## Il caso che confonde di più

C'è una variante che sembra un guasto vero e proprio: **il passaggio scatta alla prima richiesta**, quando non avete ancora scritto quasi niente. Chiedete "ciao, riassumimi questo file" e vi risponde già l'altro modello.

La spiegazione è meno misteriosa di quanto sembri. In un ambiente di lavoro — un assistente di programmazione, uno strumento agganciato ai vostri file — la prima richiesta non viaggia da sola: porta con sé il contesto. Le istruzioni di progetto, lo stato del repository, i nomi delle cartelle, pezzi dei file aperti. Se lavorate in una cartella che si chiama `pentest`, in un progetto che contiene strumenti di sicurezza, o in codice che maneggia dati biologici, il classificatore legge *quello* — e scatta sul contesto, non sulla vostra domanda. Voi avete detto "ciao"; la vostra cartella ha detto molto di più.

Una volta capito, il rimedio è quasi comico nella sua semplicità: i nomi contano. Una cartella di lavoro ordinata, un file di istruzioni che dice cosa state facendo (e per chi), meno materiale estraneo nel progetto. Non è un trucco per ingannare un controllo — è la stessa igiene che rende più precise *tutte* le risposte, perché tutto quello che il modello legge orienta tutto quello che scrive. Il classificatore nervoso è solo il primo a farvelo notare.

## Cosa farne, in pratica

**Non è un declassamento.** Il modello a cui venite passati è un modello di prima linea — su parecchi compiti, il più capace del listino. Cambiano velocità, costo e carattere, non la serietà della risposta. Se usavate Fable per la rapidità, quella la perdete per la sessione; la qualità no.

**Chi paga a consumo deve saperlo.** Il costo per richiesta cambia col modello che risponde. Un flusso automatizzato tarato sui prezzi di Fable, che per la natura del suo dominio viene instradato spesso, sta di fatto comprando un altro prodotto a un altro prezzo. È scritto tutto nella documentazione; va solo letto prima di fare i conti, non dopo.

**Chi lavora stabilmente su quelle materie può saltare il rimbalzo.** Su biologia, chimica e scienze della vita, Opus 5 risponde direttamente, senza passare la mano. Se il vostro lavoro abita lì, scegliere quel modello dall'inizio vi risparmia l'avviso, il cambio, e la piccola incertezza di ogni sessione. Il percorso "parto dal veloce e vediamo" ha senso solo se il veloce, per voi, ogni tanto è davvero disponibile.

**E vale la regola di sempre:** se su questi strumenti costruite un procedimento da cui poi dipendete, sappiate cosa fareste il giorno in cui si comporta diversamente senza preavviso. La seconda strada — un altro modello, un altro fornitore, un modello in casa — costa pochissimo finché non serve, e moltissimo il giorno in cui serve e non c'è.

## La finestra sul futuro

Resta la seconda ragione di interesse, quella meno pratica e più importante. Questo meccanismo — il modello leggero sorvegliato da classificatori, con i casi delicati deviati su modelli più controllati — non è un ripiego temporaneo: è l'assetto verso cui il settore si sta muovendo, man mano che i modelli diventano più capaci e i fornitori più prudenti. Fable è tra i primi a farlo *dichiarandolo*, con una pagina di documentazione, un avviso a schermo e l'etichetta di chi ha risposto.

Vale la pena apprezzare la trasparenza e, insieme, vedere cosa rende visibile: i confini del vostro strumento li disegna il fornitore, li ridisegna quando crede, e la vostra pratica professionale abita dentro quei confini in affitto. Fable ha il pregio di mostrarvelo con un avviso. Altri strumenti fanno lo stesso senza dirvelo.

---

*Fonte: la documentazione ufficiale di Anthropic sul cambio di modello in Fable 5 ([support.claude.com](https://support.claude.com/en/articles/15363606-why-claude-switched-models-in-your-conversation-with-fable-5)).*
