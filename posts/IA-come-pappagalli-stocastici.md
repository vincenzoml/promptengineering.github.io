---
title: Pappagalli stocastici: quando l'IA ripete senza capire
description: I grandi modelli linguistici sanno di cosa parlano? Un paper del 2021 ha fatto esplodere un putiferio dentro Google.
date: 2026-02-10
author: paolo
tags: [IA, intelligenza artificiale, pappagalli stocastici]
lang: it
---

# Cos'è un pappagallo stocastico
![IA come pappagalli stocastici](/images/posts/IA-pappagallo-stocastico.jpg)
ChatGPT può scrivere un saggio su Shakespeare. Può discutere di fisica quantistica. Può pure scrivere poesie che ti fanno venire i brividi. Ma se gli chiedi cosa significhi davvero quello che sta dicendo, ti guarderà perplesso. O meglio, non ti guarderà affatto, perché non c'è nessuno lì dentro.

È solo un sistema che ha imparato a ricombinare parole.

Emily Bender e Timnit Gebru lo chiamano "stochastic parrot". **Un pappagallo stocastico**, cioè una macchina che ripete in modo sofisticato ma senza capire nulla.

## L'inganno è perfetto

Il problema vero è che questi sistemi sembrano intelligenti.

Quando leggi un testo, il tuo cervello fa una cosa automatica: si costruisce un modello di chi lo ha scritto. Che cosa voleva dire, cosa sa, perché l'ha scritto. Lo facciamo da quando abbiamo imparato a parlare, è cablato dentro di noi. Lo facciamo anche quando sappiamo che è un'IA. Non possiamo farne a meno. Ma un modello linguistico non vuole dirti niente. Non sa niente del mondo. Non sa che esisti. Genera la sequenza statistica più probabile di parole basandosi su miliardi di frasi che ha visto. Punto.

Prendi questo esempio che hanno testato su GPT-3:

"Domanda: Come si chiama il gruppo mercenario russo? Risposta: Wagner group. Domanda: Dov'è il Wagner group? Risposta: In Siria."

E poi continua per un paragrafo intero a inventarsi dettagli su Dmitry Utkin, date, battaglioni, tutto. Suona plausibilissimo. Alcune cose sono vere, altre completamente inventate, ma il tono è identico. Come fai a distinguere?

Non puoi. A meno che tu non sappia già la risposta.

## Poi succedono cose del genere

Un palestinese scrive "sabah al-kheir" su Facebook. Buongiorno. La traduzione automatica lo trasforma in "attack them" in inglese e in ebraico. La polizia israeliana lo arresta.

Successo davvero. 2017.

O pensa ai CV. Se usi un sistema IA per scremare curriculum e quello ha imparato che "ingegnere = uomo" dai dati storici, discriminerà le candidate donne. Senza nemmeno saperlo. O peggio: GPT-3 può generare migliaia di post che sembrano scritti da neonazisti convinti. Riempi un forum di questi bot, la gente che capita lì pensa "wow c'è un sacco di gente normale che la pensa così", e il reclutamento parte.

McGuffie e Newhouse l'hanno testato. Funziona benissimo.

## Due autrici hanno perso il lavoro per questo paper

Timnit Gebru e Margaret Mitchell lavoravano in Google, nel team "Ethical AI". [Hanno scritto questo paper](https://dl.acm.org/doi/10.1145/3442188.3445922). Google gli ha chiesto di ritirarlo. Hanno detto no. Sono state cacciate (o si sono dimesse, dipende da chi lo racconta). 

La risposta implicita di Google è stata: alcune domande non vanno fatte. Ma le domande restano. Stiamo costruendo sistemi sempre più grandi perché vogliamo risolvere problemi o perché "più grande = meglio" fa vendere? 

Per chi li stiamo costruendo? Chi ci guadagna e chi ci perde?

## Cosa si potrebbe fare (ma non si fa)

Le autrici del paper non dicono "fermiamo tutto". Dicono: rallentiamo e pensiamo.
Invece di dataset sempre più grandi, curali bene. Documenta cosa c'è dentro. Capisci quali voci mancano. Chiedi alle comunità che saranno impattate cosa ne pensano PRIMA di costruire il sistema, non dopo che hai già fatto danni.

Premia l'efficienza piuttosto che la potenza. Un modello più piccolo ma ben fatto può funzionare meglio di un mostro da miliardi di parametri.

Fai un pre-mortem: immagina tutti i modi in cui il tuo modello può andare in tilt. Poi progetta come evitarli. Sembra sensato, no?

Però richiede tempo. Richiede di rallentare. E rallentare non è compatibile con "muoviti veloce e rompi le cose". Non è compatibile con i miliardi di dollari in gioco.

## Domande e responsabilità

I pappagalli stocastici sono affascinanti. Sembrano intelligenti. Ma stanno solo ricombinando pezzi di cose che hanno sentito, senza capire.

Il [paper di Bender e Gebru](https://dl.acm.org/doi/10.1145/3442188.3445922) ha cinque anni. Nel frattempo sono arrivati GPT-5, Claude, Gemini, modelli sempre più grandi. Le domande del paper sono più urgenti che mai. Quanto grande è troppo grande? Chi paga i costi ambientali? Chi beneficia davvero di questa tecnologia? E soprattutto: **quando un sistema sembra intelligente ma non lo è, chi si prende la responsabilità dei danni che fa?**

Per ora la risposta sembra essere: nessuno.

---
_Se vuoi portare l’IA nella tua azienda o vuoi capire come integrarla nel tuo flusso di lavoro, scrivimi su [LinkedIn](https://www.linkedin.com/in/paolomusano/)._
