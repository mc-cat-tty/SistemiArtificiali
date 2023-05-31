> **Vita artificiale**: declinabile come vita simulata attraverso l'informatica e ottimizzazione/risoluzione di problemi attraverso nature-inspired algorithms

Un altro esempio è la vita artificiale bagnata, che permette la risoluzione di problemi attraverso batteri e organismi viventi.

Le reti neurali si pongono sulla frontiera tra informatica e scienze cognitive (aka come funzioniamo?)

#Vedi: progetto "flagship" (nave ammiraglia) FET - Future and Emergent Technologies

>Biology is the next frontier of computer science
https://en.wikipedia.org/wiki/Eric_Schmidt

## Le tre leggi della robotica
#Vedi: _Io, robot_ di Isaac Asimov

1. Un umano non potrà mai esssere danneggiato o, nel non agire, lasciare che venga danneggiato (eg. dibattito guida autonoma: investimento guidatore - passante)
2. Un robot deve ubbidire agli ordini dell'uomo, a meno che non entrino in conflitto con la prima legge (eg. chiedere ad un GPT di creare un veleno fatale difficilmente rilevabile - entra in contrasto con la prima legge)
3. Un robot deve proteggere la propria esistenza con la sola eccezione che questo ordine non entri in conflitto con la prima o la seconda legge

## L'invincibile
Di Stanislav Lem. È un libro sugli _swarm_ molto consigliato, ambientato nella necrosfera.

# AI powered robots
## Hardware evolution
https://en.wikipedia.org/wiki/Thinking_Machines_Corporation
Componenti costitutivi:
- mattoni fondamentali di forma variabile
- strutture connettive (es: piccoli motori) per unire i mattoni
- fili per connettere i motori vicini tra loro

Lasciando evolvere questi individui, in diversi ambienti, cosa si ottiene?
Le simulazioni sono state eseguite dalla _Thinking Machines Corporation_ in ambienti che simulano terra e mare.

La fitness (livello di adattamento) di questi esseri è la distanza percorsa a parità di tempo (chiaramente da massimizzare):
- in acqua (tante soluzioni diverse con la stessa fitness)
	- l'individuo sviluppa due pinne, con un corpo centrale grande, per favorire l'inerzia, così da rimanere in asse ad ogni pinnata.
	- hippocampus (cavalluccio marino)
	- spermatozoo con coda e testa
	- serpente marino
- sulla terra
	- simil-tricheco
	- testa piccione che, mediante l'inerzia, spinge il corpo in avanti
	- serpentello

Molte soluzioni assomigliano a specie animali presenti sulla terra nel Cambriano: https://it.wikipedia.org/wiki/Cambriano

## Mind evolution
Rimane il problema del controllo -> si possono usare reti neurali per il controllo.

I building blocks sono:
- neuroni
- sinapsi
- pesi

> Evolved Neural Network

Esistono diverse codifiche, una di queste potrebbe essere il numero di strati e il numero di neuroni per strato, ammettendo che la NN sia una multi-layer perceptron.

#Vedi: _evolution of neural-controllers for flapping-wing animats_

https://en.wikipedia.org/wiki/Animat

Risultati (due strategie diverse):
- una rete neurale unica con oscillatore
- due reti neurali separate - una per ala - senza oscillatore. Viene usato un autolink (self-link) per il timing

## Ala fissa e ala battente
L'ala fissa permette di risparmiare sugli attuatori, dato che basta un rotore per muovere l'animat.

