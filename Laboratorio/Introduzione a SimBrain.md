I tool per fare AI integrano spesso strumenti per l'osservazione delle reti neurali che fanno girare.

Potremo implementare:
- cooperative networks
- feed forward
- Hopfild models

Inoltre è possibile visualizzare la rete nello spazio delle fasi.

# Componenti delle reti
## Neuroni
$$W_i = w_{i1}x_1 + \dots + w_{in}x_n$$
Tipi di neurone:
- binario -> uscita 1 o 0 (definizione a tratti con $W + b$)
	- bias -> valore b da aggiungere 
	- threshold
- lineare: $a = m(W + b)$
	- pendenza (moltiplicatore) -> m
	- bias (addendo) -> b
- sigmoidale: attivazione che segue una curva
	- tanh
	- arctan
	- logistic
- clamped: ha un valore di uscita "bloccato", ignora l'input. Si usano per la fase di apprendimento
- random: intorduce rumore nel sistema

## Sinapsi
Tipi di sinapsi:
- Hebbian: apprendimento hebbiano
- clamped: usato durante la fase di learning

# Percettroni
Neurone multilivello

## Il modello di Hopfield
Ha prestazioni inferiori rspetto ad altri modelli.
- $\alpha = 0.14$ -> coefficiente basso
- Devo avere un numero di neuroni proporzionale al numero di pattern che voglio riconoscere
- Ogni neurone collabora al riconoscimento di qualsiasi cosa (tutti fanno tutto)

I neuroni sono binari

## Rete a strati
Strato di neuroni in ingresso, strati intermedi, strato di output (classificazione)

## Percettrone semplice
Usa un iperpiano per determinare l'uscita.

## Funzioni linearmente separabili
La funzione XOR e identità non solo linearmente separabili (non possono essere divise con un solo iperpiano). Ogni iperpiano corrisponde ad un layer.

È stato di mostrato matematicamente che con uno strato nascosto è sufficiente per implementare qualsiasi rete neurale. Non è stato posto nessun limite sul numero di nodi di questo strato.

# Legenda neuroni
- rosso -> uscita
- verde -> entrata

#Vedi: radial basis function

# Shortcuts
- r -> random
- n -> nodes
- w -> weights

La morsa sta per clamp:
- N -> neurons
- W -> weights

# Fasi apprendimento
## Learning
Disegno pattern sui nodi e li blocco. Faccio evolvere i pesi.
Nodi binari, pesi hebbiani

## Inference
Disegno un carattere sporco, blocco i pesi e ottengo una configurazione stabile dei nodi.

## Aggiungere un carattere
...

# High dimensional projection
Proietto uno spazio delle fasi ad n dimensioni su uno spazio a m\<n dimensioni

#Vedi: percettroni multi-livello

# Trainer
- backpropagation -> va alla ricerca dell'errore minimo
- LMS (Least Mean Square)
I dati del trainer possono essere caricati da  _load data_


Gli **input data** sono una tabella con una colonna per ogni neurone di input.
I **training data** sono una tabella con una colonna per ogni neurone di output.

Rete di compressione con 3 layer:
- 3 nodi di ingresso
- 2 nodi intermedi
- 3 nodi di output

La compressione è possibile solo se le configurazioni di input sono meno di 8 (in questo caso). Insieme al dato da decomprimere bisogna distribuire lo strato intermedio (nodi e pesi?)

Nello XOR tiriamo casualmente i valori iniziali finchè l'errore non scende sotto al millesimo