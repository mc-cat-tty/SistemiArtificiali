# Algoritmi Genetici
Attraverso iterazioni successive si migliora il DNA mantenendo i geni positivi ed varaindo quelli negativi.

## Idea di Lamarck
Si trasmettono da una generaziona all'altra solo i caratteri migliori: i cambiamenti che avvengono durante la vita di un individuo vengono trasmessi ai discendenti.

## Darwin e Wallace
Non è vero che tutti i figli degli animali che corrono velocemente saranno veloci. -> possono nascere figli lenti da genitori veloci

Questi però non si riprodurranno -> i figli lenti vengono mangiati, abbassando la probabilità di avere una generazione successiva con più individui lenti di quella attuale

Introduce l'idea di mutazione genetica casuale che, combinata alla **pressione evolutiva**, porta al comportamento evolutivo che conosciamo.

L'evoluzione lamarckiana è più veloce di quella Darwiniana.

## Malthus
Malthus, nel campo economico, fornisce un'importante ispirazione su come funziona un sistema economico o di esseri viventi.

Senza considerare la scarsità delle risorse: $N(t+1) = N(t) + k N(t)$

Nella realtà ci si arresta ad una capacità portante (asintoto orizzontale): $N(t+1) = N(t) + k N(t) - \beta N(t)^2$

### Popolazioni in competizione
$$N = N_1 + N_2$$

Dove $N_1$ e $N_2$ hanno la propria equazione di evoluzione. Una delle due specie è destinata a scomparire.

# Genetica
Mendel intuisce il DNA: doppia elica che trasporta i geni di madre e padre.

Watson e Crick confermano l'intuizione e sviluppano la teoria.

## Dogma centrale
Il DNA è una sequenza di nucleotidi, ognuno dei quali contiene una base azotata. -> 4 livelli di memorizzazione: A, T, C, G

#Vedi: Gattaca

## Codifica
L'aminoaicido è la base della proteina. Ogni proteina è costituita da 21 aminoacidi.

Exon (esoni) -> dna muto, proteina

mRNA letto dal ribosoma. Le sequenze di aminoacidi forniscono informazioni sulla lettura dell'mRNA al ribosoma. Ogni "byte" è una tripletta di amonoacidi.

#Vedi: tRNA

L'RNA ha un tempo di vita breve, quindi viene prodotto quando serve.

## Variabilità
Mutazioni dovute agli errori di "copia":
 - Mutazioni puntiformi: 1 errore ogni 100M basi -> 20 basi modificate su ogni genoma.
 - Duplicazione di geni: può capitare che alcuni geni siano copiati due volte. **Deriva genetica**. Usata per la datazione delle specie.

Crossing-over (ricombinazione cromosomica): i geni dei figli vengono tagliati in sequenze casuali e ricombinati, scambiati.

I batteri si riproducono con una velocità non inferiore a 20 minuti. Tutti i dispositivi assessuati sono veloci nella riproduzione.

## Sintesi neodarwiniana

#Todo: da qui fino a Crossover Holland

# Algoritmi generici
## Crossover di Holland
Si parte da building blocks fondamentali e attraverso una ricombinazione + mutazione di essi si ottiene l'ottimo.


## Risovlere problemi imitando la natura
L'evoluzione non ha fine. Gli algoritmi genetici si fermano quando otteniamo una buona fitness.

1. Valutazione individuiù
2. Selezione dei più adatti
3. Ricombinazione
4. Mutazione
5. Ripetizione

## Motivo funzionamento
Holland pensa al perchè gli algoritmi genetici funzionano. I crossover sparpagliano soluzioni nello **spazio delle fasi** (proiezione in zone buone).

La mutazione permette un'esplorazione locale -> esplorazione zone vicine. La mutazione introduce novità. Dimostriamo che è utile per assurdo.

Supponiamo di voler trovare il massimo numero rappresentabile con 5 bit. Dobbiamo travare 11111. Se partiamo da una popolazione iniziale (o popolazione a tempo generico t):
 - 10001
 - 10100
 - 11101
 - 01100

In tutti questi casi in posizione 3 (partendo da 0) si trova uno 0 -> con soli crossover non si arriverà mai alla soluzione ottima.

Vedi curva di fitness: la fitness media tende a quella dell'individuo migliore. Si raggiunge l'ottimalità quando ho una popolazione omogenea, composta da individui uguali (cloni del migliore individuo trovato).

## Schemi: l'interpretazione di Holland
Ogni individuo ha una piccola intuizione, che ottimizza un sottoproblema (sottostringa).
I figli ereditano le idee del padre.

Sotto luce l'evoluzione è uno scontro di idee.

Holland chiama queste idee schemi (_schemes_)
Si può rappresentare come una soluzione con alcuni don't care: 01##1 = {01001, 01011, 01101, 01111}

Il mondo delle idee è la combinatoria dei don't care.

### Riproduzione di un singolo individuo
La probrabilità di essere scelto è il rapporto tra la sua forza e la forza di tutti gli altri individui.
$$\frac{f_i}{\sum{f_k}}$$

Forza (fitness) media di uno schema H: $f(H) = \frac{\sum_k{f_k}}{m}$

Il crossover può distruggere uno schema buono. Un'idea è tanto più facile da smontare più è lunga e più punti fissi ha -> si faboriscono gli schemi corti ad elevata fitness

Prima vengono generate idee con tanti don't care, che poi si stabilizzano di generazione in generazione.

#Vedi: slide

Idea: gli schemi con alta fitness si diffondono esponenzialmente

# Convergenza prematura
Fenomeno in cui una soluzione sub-ottimale colonizza l'intera popolazione. Se non ci fosse crossover si replicherebbero gli schemi migliori, ma mancherebbe la diversità.
La fitness media diventa uguale alla fitness massima.

Si usano tecniche per rallentare la convergenza

# Nicchie
- Nella realtà gli individui si riproducono con individui della stessa zona (**località degli individui**)
- Inoltre i figli rimangono circa nella stessa area in cui abitano i genitori.
- I conflitti sono risolti in modo dipendente dalla forza dei contendenti

I genomi con alta fitness prima di confrontarsi con genomi distanti devono arrivarci, superando molti conflitti.

Questo meccanismo perserva la diversità -> rallenta l'evoluzione

La scelta dei genitori proporzionale alla fitness rappresenta bene quello che succede in natura, ma ha degli svantaggi: possibile scomparsa di individui molto performanti.

Con una scelta a caso, una volta arrivati vicino alla convergenza, potrei scegliere un individuo che non è il migliore per la riproduzione.

# Elitismo
> Garantisce la sopravvivenza degli individui con fitness più alta.

Questo velocizza la convergenza. Per arginare il problema ho diverse tecniche:

### Scaling
Selezione selezione degli individui secondo metriche **non lineari** dalla fitness (es: quadratica, cubica), per esaltare le piccole differenze.

Quindi $p_i = \frac{f_i}{\sum_j{f_j}}$ si trasforma in $p_i = \frac{F(f_i)}{\sum_j{F(f_j)}}$ con $F(X)$ uguale a $x^2$, $x_3$, ...

### Selezione per rango
>Ordino gli individui per fitness (ordine decrescente). Uso un **ranking** con distribuzione di punteggio costante, indipendente dal valore di fitness.

La selezione a questo punto può lavorare sui ranking al posto che sul valore di fitness

Vantaggi:
- nessun individuo ha una probabilità molto maggiore di essere selezionato
- #Todo

### Scelta per torneo
Scelgo casualmente s individui dalla popolazione di N individui, #Todo 

# Varianti
Posso aggiungere **punti di taglio**, non è obbligatorio averne 1 solo.

#Todo 

È possibile usare una **codifica discreta**, quindi non necessariamente binaria. Ogni posizione può essere occupata da un simbolo che appartiene ad un alfabeto con k>2 simboli, oppure una codifica in numeri reali.

L'operatore di mutazione deve essere **modificato** come di seguito:
- per **caso discreto**: si sceglie una posizione e si sistituisce il simbolo in quella posizione con uno dei possibili k-1 simboli restanti, scelto a caso
- per **caso continuo**: #Todo 

Esistono molte altre varianti.

# Algoritmi genetici per l'ottimizzazione
La **fitness** coincide con la **funzione di costo**

Alternativa all'ascesa del gradiente.

#Todo 

## Ricerca di minimi e massimi
Da immaginare come la ricerca della cima più alta di una catena montuosa

### Problemi non risolvibili
Non sono risolvibili problemi come la ricerca di un ago in un pagliaio

### Problema del commesso viaggiatore
Non posso rappresentare gli individui come una lista \[A, B, C, D\] di nodi da visitare, perchè facendo crossover potrei ottenere sequenze illegali, in cui ad esempio si ripete più volte un figlio.

#### Crossover a mappa parziale
Per ottenere tour legali posso pensare al crossover come ad una mappa di scambio che permuta i figli.

### Altre applicazioni
- classici problemi di ottimizzazione combinatoria
- ottimizzazione di parametri di un modello dinamico (biorisanamento terreni)
- logistica: instradamento di veicoli in finestre temporali
- scheduling: orari scolastici
