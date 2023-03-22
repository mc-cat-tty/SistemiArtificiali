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
Ogni patch ha delle coordinate -> `pxcord, pycord` -> intere
`pcolor` modifica il colore

(0, 0) è l'origine.

Il mondo è **toroidale** (world wraps hor and vert).

Stessa cosa per le turtles, ma con coordinate non necessariamente intere (possono stare a cavallo di più patches)

# Turtle built-in
- breed
- color
- heading
- hidden? -> 
- label
- who -> id integer >= 0, riciclati dagli agenti morti

TODO: completa built-in di turtles e patches, logo programming language