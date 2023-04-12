Vediamo l'implementazione di stormi, termitai, alveari e altre creature collettive
Anche i branchi di pesce (aringhe)

Queste creature collettive riescono a scacciare i predatori

# Boids
https://en.wikipedia.org/wiki/Boids

3 regole:
- **separazione** -> distanzialmento per non interferire il volo (movimento delle ali, ma anche delle pinne)
- **coesione** -> per animali sociali e non solitari come i falchi
- **allineamento** -> cambiare la direzione per allinearsi agli altri in volo

La regola di coesione moderna prevede la coordinazione con solamente con i 5/10 uccelli più vicini/più simpatici

Ogni boid reagisce solo ai compagni di volo vicini, entro un certo raggio dalla loro posizione. In più hanno un angolo cieco dietro di loro.

Come gli stromi di uccelli che si appollaiano a Roma, i boids si possono programmare per accoccolarsi sui bordi di un'immagine, o in generale su zone "calde" (di particolare interesse).

# Ant sorting
Intuizione: struttura di un formicaio ottenuta versando ferro fuso nel terreno ed estraendo il risultato, ovvero la forma del calco

Si vede che i magazzini dei formicai sono ben organizzati e suddivisi per compiti, con una gerarchia ben precisa. Le formiche hanno qualche centinaio di neuroni, ma riescono ad organizzare il cibo.

Algoritmo:
- casualità necessaria per fare vagare le formiche nel formicaio come una sorta di moto browniano. Questo permette l'esplorazione, anche totale con sufficiente tempo
- se capito su una patch dove si trova del grano, lo raccolgo
- cammino casuale
- se mi trovo su una patch vuota lo rilascio

È più probabile che da un magazzino piccolo si porti in un magazzino grande -> feedback negativo

Situazioni stabili:
- se le aree morte tra due magazzini sono molto distanti rimangono dei gruppetti separati
- se i magazzini sono molto vicini tra loro si arriva alla convergenza (un unico magazzino che raccoglie tutto)

Se il mondo smette di essere toroidale (aggiunta pareti) i cumuli si addensano sulle pareti, in particolare sugli spigoli.

## Modello delle termiti
1. Cerca cibo
	1. una termite scarica controlla se c'è cibo sulla patch sottostante
	2. se c'è cibo lo preleva e va avanti
	3. altrimenti fa un passo a caso (angolo casuale) e torna al passo 1
2. Appoggia cibo
	1. se la patch sottostante è libera appoggio il cibo
	2. altrimenti mi allontano

## Comandi utili
- `random-xcor` e `random-ycor` per coordinate casuali all'interno del mondo
- `setxy` imposta le coordinate di una turtle