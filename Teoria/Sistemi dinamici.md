> I sistemi dinamici sono sistemi che variano nel tempo

Esempi di sistemi naturali:
- corpo che cade
- formicaio
- colonie batteriche
- ...

Caratteristiche:
- determinismo
- probabilità
- irreversibilità

Vedi: **attrattori**

È fondamentale accorgersi della regolarità dei fenomeni per fare **previsioni**

Nell'astronomia aristotelica si calcolano le orbite conoscendo il moto uniforme dei pianeti.
=> I **moti retrogradi** sono inaspettati (rotazione intorno all'epiciclo)

https://it.wikipedia.org/wiki/Epiciclo_e_deferente

Nasce il sistema Tolemaico.

Vince si quest'ultimo il sistema Copernicano perchè più semplice: modello eliocentrico con orbite circolari. -> dibattito. Vedi: rasoio di Occam
https://it.wikipedia.org/wiki/Rasoio_di_Occam

Poi viene dimostrato che le orbite ellittiche. Conferma di Galileo.

Viene scoperto Nettuno seguendo le leggi di Newton.

Le leggi della dinamica vengono estese ai mezzi continui come fluidi e solidi

Unificazione delle leggi di maxwell, faraday ecc. all'ottica

## Paradigma della meccanica classica
Mondo **deterministico** e **reversibile**: date le condizioni iniziali e la lagge, posso prevedere il futuro.

*Demone di Laplace*: osservatore di ogni particella dell'universo che può prevederne il futuro

# Moto browniani
Brown era un biologo. Studia la traiettoria di un granello di polvere.

Il granello è soggetto al rumore, vedi grafico.

# Reversibilità del tempo
Nella meccanica classica esiste l'invarianza rispetto all'inversione temporale.

Il mondo reale è tutt'altro che reversibile => direzione temporale. Irreversibilità

## Urna di Ehrenfest
Deriva dal seguente modello: gas contenuto in una camera che si espande verso una camera senza gas, fino ad espanderne tutto il volume.

Ho due urne, estraggo una pallina dall'urna di sinistra e la sposto a destra, ma posso fare anche il contrario.

Ho tante palline ($10^{20}$) -> ho due possibili descrizioni:
- microscopica: un vettore binario con tante posizioni quante sono le palline. Ogni posizione indica la posizione della pallina (0 a destra e 1 a sinistra)
- macroscopica: seguo il percorso di una sola pallina
	- Inizio: N1 = N e N2 = 0
	- Non ho una situazione finale
Raggiungo l'equilibrio quando ho tante palline a sinistra quante ne ho a destra.

Ottengo una sorta di esponenziale inverso che tende asintoticamente a N/2. È lo stesso andamento del decadimento radioattivo.

L'equazione macroscopica è: $n = N_1-N_2$ => $n'(t) = Ne^{-kt}$

### Osservazioni
Su scala macroscpica il fenomeno NON è reversibile e deterministico, arriverò a $N_1-N_2 = 0$ per t tendente a infinito.

Sulla scala microscopica è reversibile e stocastico.

Su scala **mesoscopica** (dimensione intermedia tra scala micro e macroscopica) è irreversibile e stocastico.

# Sistemi lineari
I sistemi più interessanti per noi sono quelli non lineari, irreversibili.

Partendo dall'equazione differenziale $\frac{dx}{dt} = kx$
Una funzione la cui derivata è uguale a se stessa è l'esponenziale: $x(t) = Ae^{kt}$ perchè vale anche se 

Con il parametro decido la direzione dell'esponenziale (ottengo anche una costante con k=0).

Nei sistemi lineari il risultato della soluzione è la somma delle soluzioni parziali.

## Sistemi dinamici
Vedi: attrattore -> segmento e punto medio

## Sistemi dissipativi
Partiamo da un pendolo ideale e dal suo grafico angolo-velocità

Otteniamo:
![[sistema_dinamico.png]]


Aggiungiamo l'attrito e ottieniamo che la velocità viene smorzata man mano, l'angolo si "chiude" verso il centro (angolo = 0) -> attrattore del sistema
![[sistema_dissipativo.png]]


## Spazio delle fasi
TODO

## Stabilità
Equilibrio stabile o instabile. I punti di stabilità sono di nostro interesse.

Ottengo un OCR per il riconoscimento del testo: i punti di equilibrio/stabilità sono le risposte corrette (caratteri), i caratteri sporchi vengono ricondotti a caratteri buoni

# Popolazioni interagenti
Abbiamio volpi e conigli. Le volpi mangiano i conigli.

Modellato da:
$$\begin{pmatrix} \dot n_{1}(t) \\ \dot n_{2}(t) \end{pmatrix} = \begin{pmatrix} a_{11} & a_{12} \\ a_{21} & a_{22} \end{pmatrix}  \begin{pmatrix} n_{1}(t) \\ n_{2}(t) \end{pmatrix}$$

In base ai coefficienti a che scelgo (con a<0 approccio "distruttivo") ottengo:
- parassitismo se discordi
- cooperazione se concordi positivi
- competizione se concordi negativi

Se n1 e n2 fossero uguali a t otterrei come soluzioni (0, 0) -> estizione, impossibile

Quindi $n_i(t) = e^{\beta_it}$
Variando i coefficienti $\beta$:
- punto a sella (oensa a montagna) se discrodi -> in una direzione attrattivo, nell'altra repulsivo
- punto repulsivo se negativi concordi
- punto attrattivo se positivi concordi

Questi sono gli unici casi possibili in mondi lineari

# Ciclo limite
Pensa l'orologio a pendolo (caricato ogni mattina con la molla)
Ad ogni giro viene data una piccola spinta dal martelletto (caricato a molla).
Da qualsiasi angolo io parta torno sempre allo stesso ciclo. Il pendolo raggiunge la stabilità quando l'energia data dal martelletto eguaglia quella persa dal giro di pendolo.

Questo non è un sistema lineare (non ha un punto di stabilità)

Centri e cicli limite esistono in mondi non lineari a due o più variabili.

# Sistemi caotici
Effetto farfalla e Lorentz. Lorentz cerca di creare un modello per previsioni metereologiche (anni '60). L'istituto dove fa ricerca compra un nuovo computer, risolve l'algorimo più volte su computer diversi e ottiene risultati diversi: bel tempo e uragano. Algoritmo deterministico, risoluzione pure, differenti condizioni iniziali.

Uno ha una parola di 16 bit, l'altro da 32 bit. Condizioni diverse perchè le ultime cifre della rappresentazione floating point.

>Il battito di ali di una farfalla a Chicago generava un uragano il giorno dopo a New York

**Caos deterministico**: una differenza piccola nelle condizioni iniziali viene amplificata.

Ho un attrattore "strano" o caotico -> non è un punto fisso

![[sistemi_caotici.png]]
Questa curva non sarà mai uguale a se stessa. Sembra quasi periodica, ma è imprevedibile. È servita una simulazione.

Nell'esempio le due ali corrispondono a:
- bel tempo
- uragano
