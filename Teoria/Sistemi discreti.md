Anche i sistemi discreti nel tempo si suddividono in lineari e non lineari. Il computer non riesce a lavorare con valori continui. Es: non pretendo di avere derivate perfette.

# Sistemi unidimensionali discreti nel tempo
Equzione per dinamica delle popolazioni, decadimento radoattivo, ecc.

$x_{t+1} = kx_{t}$

Per t passi possiamo scrivere: $k^{t}x_0 = ... = e^{ln(x^t)}x_0 = e^{tln(x)}x_0$ in cui posso rinominare $ln(x)$

TODO

## Caso studio: riproduzione dei conigli
Il mondo dei conigli può essere modellato con una equazione lineare.

Per gli esseri umani consideriamo una generazione ogni 25 anni. In ogni secolo possiamo avere solo 4 generazioni.

Modellando (**modello fenomenologico**) solo le morti e le nascite (non l'interazione con l'ambiente, come ad esempio la carenza di cibo): $x_{t+1} = x_t + bx_t - dx_t$
_Gli individui all'istante t+1 sono gli individui all'istante precedente + nascite - morti_
=> crescita illimitata

Nella realtà più siamo più è grande la frazione di quelli che moriranno; non sono una frazione costante.

Più realistico: $(1+b)x_t - dx_t^2$
- b termine di controllo per le nascite
- d termine di controllo per le morti -> quando siamo tanti prevale lui

### Modello di Verhulst
La crescita si ferma al *livello di saturazione* o _capacità portante_ -> K

Rinominando i coefficienti ho:
- $(1+b) = B$
- $d = A$
Imponiamo $A=B$: $x_{t+1} = Bx_t-Ax_t^2 = Ax_t(1-x_t)$

### Mappa logistica
Cerchiamo i punti di stabilità (attrattore): $x_{t+1} = x_{t}$ -> $x = Ax(1-x)$
![[punti_fissi_conigli.png]]

0 è un punto fisso repulsivo. Appena ho due o più conigli vado al secondo punto fisso.
Con A piccolo la parabola è schiacciata: potrei non avere il secondo punto fisso.

Posso vederlo graficamente (*metodo della scala*):
![[metodo_della_scala.png]]

Il punto fisso in questo caso è inferiore alla capacità massima.

Il punto è stabile solo se ogni successiva perturbazione è inferiore alla precedente.

### Crescita di Feigenbaum
Scoperta di **Feigenbaum** a Santa Fe.

Con A>3: rimbalzo tra due punti fissi. Applicando la funzione 2 volte torrno ad un punto fisso
Con 3 < A < 4: ho quattro punti fissi
Con A = 4: ho otto punti fissi
Con A grandi non ottengo dati significativi (sembra)

Questo sistema è usato dai *generatori di numeri casuali*.

Il rapporto tra la distanza di una biforcazione e l'altra è costante
![[feigenbaum.png]]

Tende alla costante di Feigenbaum (**crescita di Feigenbaum**): $A_\infty = 3,5699$
Ho infiniti punti di equilibrio fino ad arrivare alle fasce bianche, in cui il sistema esce dal caos. Ha un numero finito di punti di stabilità.

# Esperimento di Libchaber
Instabilità fluidodinamica: formazione di roll in condizioni controllate.
Celle di Benard

Nei mondi discreti esiste il caos (dipendentemente dai parametri scelti).

# Potenziale
Non esiste (semplificazione). Astrazione matematica.

$\frac{dx}{dt}=f(x)=-\frac{dV}{dx}$
V è la funzione potenziale, derivata, cambiata di segno, dà la regola di cambiamento f(x)

V è uguale alla funzione di cambiamento derivata e cambiata di segno. Il cambiamento di segno è dovuto al fatto che la pallina "scende" rispetto alla direzione in cui la curva sale.
![[potenziale.png]]

Il sistema si muove (come una pallina) finchè non raggiunge un minimo di energia.

Lo uso per lo studio degli stati di equilibrio del sistema.

## Doppia buca
$\frac{dx}{dt} = -ax-bx^3$

Parte lineare + termine di controllo cubico

Risolviamo in $\mathbb{R}$:
- $x=0$
- $x=\pm\sqrt{\frac{-a}{b}}$

Con a positivo ho un solo punto di stabilità (altrimenti sfocerei nei numeri immaginari), con a negativo ne ho tre.

Con:
- a > 0 è stabile -> **singola buca**
- a < 0 è instabile, il sistema ricade negli altri due punti -> **doppia buca**
![[potenziale_buca.png]]

Il secondo caso equivale ad un pendolo inverso. La scelta della direzione dipende dal rumore. Rottura del potenziale.

Vedi: Segway, XAI - Explainable Artificial Intelligence

# Visione sugli argomenti futuri
Partiremo dalle scienze sociali, che studiano le interazioni tra gli agenti.