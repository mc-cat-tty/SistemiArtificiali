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