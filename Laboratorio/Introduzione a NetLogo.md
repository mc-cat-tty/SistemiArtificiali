Ogni libreria (modello fatto da altri) ha 3 sezioni:
- interfaccia
- informazioni
- codice

Il monitor riporta statistiche sul mondo degli agenti

#Nota: meno lucciole, più tempo di "convergenza", senza casualità non si sincronizzano
#Vedi: flashing fireflights

NetLogo è un linguaggio di programmazione **agent-based** + ambiente di modellazione integrato.

=> esplorazione di comportamenti emergenti

# Tipi di agenti
- turtles: triangoli, possono muoversi
- patches: quadratini che derivano dall'intersezione tra gli assi e servono per simulare il mondo
- links: entità che collega altri agenti (molla)
- the observer (fumetti Marvel): agente esterno che può imporatire ordini al sistema o estrarre statistiche

# Sistema di coordinate
Patch e turtle hanno delle coordinate, nel primo caso intere, nel secondo caso volendo frazionarie.

(0, 0) è l'origine.

Il mondo è **toroidale** (world wraps hor and vert) => sulle frontiere succedono spesso cose strane

# Patch
- `pcolor`
- `plabel`
- `plabel-color`
- `pxcor` intera
- `pycor` intera

#attenzione: lo spazio è un separatore, gli operatori matematici no (`test-var` diverso da `test - var`)

# Turtle
Stessa cosa per le turtles, ma con coordinate non necessariamente intere (possono stare a cavallo di più patches).

Le turtle sono agenti di classe superiore, perchè possono modificare anche lo stato interno delle patch (o di altri agenti in genere).

- `breed`: per creare nuovi tipi di agenti
- `color`
- `heading`: direzione della tartaruga
- `hidden?`: indica se la tartaruga è visibile (boolean)
- `label`
- `pen-mode`: contiene lo stato del pennarello della tartaruga (sollevato o abbassato)
- `pen-size`: larghezza della penna
- `shape`: forma della tartaruga, volendo icona personalizzata
- `size`
- `who`: id integer >= 0, non vengono riciclati

#vedi: Logo programming language, turtle Python module (Achille e la tartaruga)

I valori ammissibili di `pen-mode` sono:
- "up"
- "down"
- "erase"
- pen-down
- pen-up
- pen-erase
- pd
- pu
- pe

# Variabili
## Tipologie
- global variable: accessibile da tutti gli agenti. `globals[score]`
- turtle variable: `turtles-own[energy speed]` -> aggiunge variabili allo stato interno di tutte le tartarughe
- patch variable: `patches-own[friction]`
- link variable: `links-own[strength]`

#nota: elenchi di variabili non richedono di separare gli elementi con la virgola

#vedi: reporter function -> ritorna un _agent set_

## Impostazione
```NetLogo
ask turtles [ set pcolor red ]
```

`ask` è una keyword fondamentale, in quanto si _chiede_ agli agenti di fare qualcosa.

Questo snippet non fa quello che si pensa: imposta il colore della patch sottostante a tutte le tartarughe a rosso.

## Lettura
```NetLogo
show [color] of turtle 5  ; stampa il colore attuale della tartaruga con ID 5
```

#attenzione: `of` è una keyword

## Slider
Gli slider possono essere associati a variabili globali, modificabili direttamente dall'interfaccia

# Procedure e funzioni
Primitive di NetLogo:
- `command` (`procedure`): azione che gli agenti devono portare a termine
- `reporter`: calcola un risultato e lo riporta

I comandi sono introdotti dalla keyword `to`:
```NetLogo
to setup
	clear-all
	crt 10  ; abbreviazione di "create-turtles"
end
```
Questo snippet crea una procedura `setup` il cui contenuto è definito dall'utente.

```NetLogo
to go
	ask turtles
	[fd 1  ; forward di 1 passo
	rt random 10  ; rotazione verso destra di un valore casuale tra 0 e 9 (inclusi)
	lt random 10]  ; rotazione verso sinistra
end
```
Questo snippet definisce una procedura `go`.

`random` e `turtles` sono esempi di reporter, perchè hanno un valore di ritorno.

Il generale la sintassi per definire una procedura è:
```NetLogo
to procedure_name [arg1, arg2, arg3]
	...
end
```

La cui invocazione sarà: `procedure_name 1 2 3`

Mentre il reporter, che a differenza di una procedura ritorna un valore, può essere definito come:
```NetLogo
to-report reporter_name [args]
	...
	report val
end
```

#Attenzione: per ritornare l'opposto di un valore numerico occorre usare uno spazio tra il meno e il valore -> `report (- val)`


# Costrutti condizionali
```NetLogo
if COND [
	...
]
```


```NetLogo
ifelse COND [
	...
] [
	...
]
```

# Commenti
I commenti inline devono essere preceduti da `;;`

# Ask
> NetLogo è il linguaggio della gentilezza. Per ottenere una cosa è necessario chiederla.

```NetLogo
ask CONTEXT [ ... ]
```

Possibili contesti:
- observer
- turtles
	- `turtles`
	- `turtle WHO` con WHO pari a 1, 2, ..., N
- patch
	- `patches`
	- `patch pxcor pycor`
	- `patch_at xrel yrel` posizione relativa, per esempio rispetto ad un turtle
- links

## Ask concurrent
```NetLogo
ask-concurrent CONTEXT [ ... ]
```
Implementa un meccanismo di turn-taking, in cui durante ogni turno un agente può eseguire una sola azione. Quasi tutte le operazioni vengono considerate un'azione singola, ad esclusione dei movimenti (`forward` - `fd` e `backward` - `bd`) di N passi, i quali non sono atomici. Ad ogni turno una turtle potrà avanzare di 1 solo passo.

Gli **agentset** (contesti) definiti in NetLogo sono turtles, patches, links.
Possono essere estratti degli **agent subset**:
- `turtles-at`: tutte le tartarughe su una patch relativa
- `turtles-here`: tutte le tartarughe sulla stessa patch
- `turtles-on`
- `other turtles`: tutte le tartarughe escluse se stessa
- `other turtles-here`: tutte le altre tartarughe su questa patch
- `as in-radius R`
- `as at-points [p1 p2 p3]` dove ogni punto è qualcosa formattato come `[x y]`
	- `as at-points [[0 1] [1 0] [0 -1] [-1 0]]` è equivalente a `neighbors 4`
- `as with [RULE]`. Es: `as with [color = red]`