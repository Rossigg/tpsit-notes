--- 
title: "Diagramma degli Stati"
description: "Descrive il comportamento dei sistemi" # aggiorna testo !
date: 2021-02-25T15:57:21+01:00 # aggiorna data !

draft: true # cambia con false quando viene approvata la versone definitiva !

languageName: "Italiano"
author: ["Giacomo", "Nicolò", "Lorenzo", "Stefano"] 

tags: ["Requisiti Software"]   
categories: ["Requisiti Software"]   
---  

<!-- Write content Down Here :) -->

<!-- placeholder text || you can use Markdown or HTML to add some content -->

Un **diagramma di stato** è costituito da *stati*, *transizioni*, *eventi*e *attività*. Si utilizzano diagrammi di stato per illustrare la **visualizzazione dinamica** di un sistema. Sono particolarmente importanti nella modellazione del comportamento di un'*interfaccia*, una *classe* o una *collaborazione*. I diagrammi di stato enfatizzano il **comportamento ordinato** per evento di un oggetto, che è particolarmente utile nella modellazione di sistemi reattivi.

# Simboli e notazioni del diagramma di stato di base

## Stato

Uno **stato** è una condizione durante la vita di un oggetto durante la quale *soddisfa una certa condizione*, *esegue un'attività* o *attende un evento esterno*.

![State_simple](State%20Diagram/State_simple.svg)
Lo stato è rappresentato da un rettangolo
![State_complex](State%20Diagram/State_complex.svg)
Uno stato con delle attività

## Stati iniziali e finali

- Lo **stato iniziale** di un diagramma della macchina a stati, noto come *pseudo-stato iniziale*. Una *transizione* da questo stato mostrerà il **primo stato reale**.

![InitialState](State%20Diagram/InitialState.svg)
Un cerchio pieno seguito da una freccia rappresenta lo stato iniziale

- Lo **stato finale** di un diagramma della macchina a stati. Una macchina a stati ad *anello aperto* rappresenta un oggetto che può *terminare prima che il sistema termini*, mentre un diagramma di macchina a stati ad *anello chiuso* *non ha uno stato finale*; in tal caso, l'oggetto rimane in vita fino a quando l'intero sistema non termina.

![FinalState](State%20Diagram/FinalState.svg)
Una freccia che punta ad un cerchio pieno circoscritto in un altro cerchio rappresenta lo stato finale

## Evento

Un **evento** è la *specifica* di un *evento significativo*. Per una macchina a stati, un evento è il verificarsi di uno stimolo che può attivare una transizione di stato.

## Azione

Un'**azione** è un *calcolo eseguibile*. Le azioni possono includere *operazioni*, la *creazione* o la *distruzione* di altri oggetti o l'*invio* di segnali ad altri oggetti.

## Transizione

Una **transizione** è una *relazione* tra *due stati* indicante che un oggetto nel *primo stato*, quando un insieme specificato di eventi e condizioni *è soddisfatto*, eseguirà determinate *azioni* ed entrerà nel *secondo stato*.

Una transizione ha :

1. stato di origine
2. trigger di evento
3. azione/i
4. stato di destinazione

![Arrow](State%20Diagram/Arrow.svg)
Una linea retta rappresenta il percorso tra stati differenti

```text
Una **transizione automatica** è una transizione i cui stati di *origine* e di *destinazione* sono gli *stessi*
```

# Concetti avanzati del diagramma di stato

## Vincoli

È possibile aggiungere **vincoli** alle transizioni, la semantica è che una transizione è *abilitata* quando il vincolo è *vero*.

![Contraint](State%20Diagram/Contraint.svg)
I vincoli "[non ultima copia]" e "[ultima copia]" vengono utilizzati per distinguere le due transizioni con l'evento "copyBorrowed ()"

## Sottostati

Un **sottostato** è uno che *non ha sottostruttura*. Uno stato che ha *sottostati* (stati annidati) è chiamato **stato composto**. Gli stati secondari possono essere annidati a qualsiasi livello. Una macchina a stati annidata può avere al massimo uno stato iniziale e uno stato finale. I sottostati vengono utilizzati per semplificare macchine a stati flat complesse mostrando che alcuni stati sono possibili solo all'interno di un contesto particolare.

![Substates](State%20Diagram/Substates.svg)
Lo stato composito Raffreddamento ha 3 stati nidificati (sottostati) che vengono eseguiti in sequenza

## Stati nella storia

Quando una transizione entra in uno *stato composto*, l'azione della macchina a stati annidata *ricomincia* dallo *stato iniziale*. Gli **stati della cronologia** consentono alla macchina a stati di **rientrare nell'ultimo sottostato attivo** in essa prima di lasciare lo stato composto.

![HistoryState](State%20Diagram/HistoryState.svg)
Lo stato della cronologia è rappresentato da una H in un cerchio

## Stato concorrente

I **sottostati simultanei** sono *indipendenti* e possono essere completati in momenti diversi. Ogni stato secondario è separato dagli altri da una linea tratteggiata.

![ConcurrentState](State%20Diagram/ConcurrentState.svg)
Nello stato On 4 stati nidificati vengono eseguiti in 2 parallelismi diversi. I 2 sottostati sono divisi da una linea tratteggiata

# Esempio

Ecco un esempio della vita del processo in una CPU.

Quando un **nuovo processo** è pronto per *l'esecuzione*, verrà **spostato nella coda di attesa** dove attende l'assegnazione della CPU. Quando la *CPU è libera* per questo processo, verrà **spostato nella coda in esecuzione**. Nello stato di esecuzione possono verificarsi 2 casi: il *processo ha terminato o ha terminato la sua vita*, quindi verrà **spostato fuori dallo stato di esecuzione**; oppure la *risorsa non è disponibile*, quindi verrà **spostato nella coda di blocco** e quando la *risorsa viene liberata*, verrà **nuovamente spostato nella coda di attesa**.

![CPUStateDiagram](State%20Diagram/CPUStateDiagram.svg)
Diagramma di Stato - Esecuzione della CPU
