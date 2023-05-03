Il problema di sistemi esperti e LCS è il rumore: _domare gli attrattori_

Bacino di attrattori -> la risposta corretta va verso gli attrattori
Bio-ispirate: come i neuroni umani se viene sovrastimolato (soglia superata), si attiva

#Vedi: Hebbian theory, grandmother neuron

Il riconoscimento di oggetti, persone e voci nel nostro cervello non fa attivare un solo neurone, ma diverse aree di esso.

I neuroni specchio si attivano quando vedo una persona che compie un'azione o che ha una reazione ad un "input". A questo punto mi si attivano processi come se fossi io in prima persona ad essere soggetto allo stimolo.

# McColluch e Pitts
Pionieri delle reti neurali: 1 solo neurone a 2 livelli. Neurone booleano (0, 1 oppure -1, 0)

Ad ogni neurone arrivano in ingresso diversi input, con un peso associato: $I = w_1 x_1 + w_2 x_2 + \dots + w_n x_n$

Questo modello permette di costruire una porta logica per ogni neurone:
- OR -> ogni ingresso ha peso 1, soglia 0.5
- AND -> ogni ingresso ha peso 1, soglia 1.5
- NAND -> ogni ingreso ha peso -1, soglia -1.5
- AND NOT -> pesi 1, -1, soglia 0.5
- XOR (attiva se input diversi) -> serve uno stato aggiuntivo (percettroni) -> Due layer: AND e OR

## Modello di Hopfield
Si ispira agli spin dei campi magnetici

#Todo

## Funzione energia
$$E(x) = \frac{1}{2}\sum_{i,j=1,i \neq j}^Nw_{ij}x_ix_j + \sum_{i=1}^N \theta_ix_i$$

I punti di minima energia sono gli attrattori

Questa è una funzione di **Lyapunov**, ovvero una funzione che cala sempre. L'energia totale del sistema cala finchè non raggiunge un attrattore.

#Todo: vedi dimostrazione. Nota che ad ogni passo cambia un solo neurone

## Apprendimento hebbiano
Da Donald Hepp (1949), neurologo. Quando un assone di una cellula eccita ripetutamente un'altra cellula, allora si verifica un processo di crescita e rinforzo.

Allo stesso modo se due neuroni si attivano in sincrono, allora il loro lagame va rafforzato.

#Vedi: esperimento di Pavlov con i cani -> riflesso incondizionato: crea legame tra l'area dell'udito e quella della digestione. Aumenta fisicamente lo spessore delle sinapsi.

Se sono in **antifase** uno si spegne e l'altro si accende, se sono in fase (entrambi accersi o spenti) si rafforzano.

Insegnando un pattern $A = (a_1 \dots a_N)$ le sinapsi dei neuroni nello stesso stato aumentano di valore. Una soluzione potrebbe essere $\Delta w_{ij} = (2A_i - 1) (2A_k - 1)$

Possiamo usare una rete neurale anche per riconoscere se un pixel è di tipo A, B, A', B'

# Note sul modello di Hopfield
Nel modello di Hopfield la forma corretta, per esempio, di una lettera può essere dedotta da lettere scritte male. Grazie alla messa in and (**sovrapposizione**) delle uscite dei vari neuroni si ottiene la resistenza al rumore.

#Vedi: archetipi