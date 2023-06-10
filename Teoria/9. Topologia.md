# Esempi storici
## Mafia Boy
Michael Calce, canadese, nel 2000 satura le connessioni delle big tech americane con un DDOS. Le richieste arrivarono da centinaia di migliaia home computer alle 10:20 PST.

## Damasco
Paolo di Tarso deve diffondere un messaggio nell'Impero Romano di occidente.
Diffonde la voce nelle città più importanti dell'epoca (si trovavano all'intersezione tra strade, avevano porti, ecc.).

Paolo, a differenza degli apostoli, ha una visione e capisce la struttura del suo mondo. Cambia completamente la scala di diffusione.

Morale:
> Nothing happens on isolation

# Topologia
## Konigsberg
I grafi nascono con Eulero nel 1736, quando deve risolvere il problema dei ponti di Konigsberg.

- Eulerian trail/path -> percorso che visita ogni arco del grafo esattamente una volta
- Eulerian circuit -> percorso euleriano che parte e termina sullo stesso vertice

## Party
Persone che parlano insieme a tavola

## Cluster
Da un universo casuale emerge un cluster

Plot numero di archi - dimensione cluster più grosso. Quando ho circa 1 link per nodo, il sistema è praticamente connesso, poiché al passo successivo avrò la rete quasi totalmente connessa.

# Metriche per valutare una rete
## Percorso dell'informazione
Classe dei percorsi minimi.

La **lunghezza caratteristica di un percorso** è la distanza media (mediana delle medie delle lunghezze) che bisogna percorrere per connettere due nodi casuali.

Il **diametro** di un grafo è la massima delle distanze massime tra due nodi.

## Tempo di diffusione caratteristico di una rete casuale
Data una rete con nodi che hanno in media $k$ link, in $d$ passi possiamo raggiungere tipicamente $k^d = N$ nodi.

L'aggiunta di un nodo dopo la **percolation threshold** (soglia di percolazione, numero di nodi dopo il quale la rete "esplode").

Con la formula inversa si ottiene che: $d = \frac{logN}{logk}$
Osservazioni:
 - se la dimensione della rete aumenta di 100 nodi ($N = 100$) il numero di passi che servono per raggiungere tutti i nodi aumenta di un fattore 2
 - non esistono reti più veloci di quelle casuali. Solo le reti ultraveloci, che non hanno struttura completamente casuale, possono raggiungere velocità maggiori.

## Coefficiete di clustering
> Gli amici dei miei amici sono connessi?

Formalizza il concetto di vicinato.
Se è alto posso rimuovere nodi mantenendo **ridondanza** nella rete.

Un **d-lattice** (se $d=2$ è una griglia) è molto lento ma molto robusto, quindi con molta ridondanza. Una rete circolare è veloce ma ha bassa ridondanza. Si cerca un tradeoff tra le due topologie. In generale le **reti regolari** offrono ridondanza (percorsi alternativi) ma sono dannatamente lente.

#Vedi: logistic function (caso particolare del sigmoide)

## Reti sociali
Una soluzione per il trade-off robustezza e velocità ci viene proposto dalle scienze sociali.

#Vedi: I gradi di separazione (degrees of separations)

Nel 1967 Milgram's fa l'esperimento mentre lavora per la Harvard University:
1. manda una lettera a punti a caso degli Stati Uniti
2. ad ogni persona viene richiesto di consegnare la lettera a sua moglie (o, nel caso in cui non la conoscesse, ad una persona che pensa possa conoscerla)
3. firma ad ogni passaggio

Su 160 lettere inviate ne arrivano 42 con una mediana di 5.5 firme. Nell'89 esplode il web.

