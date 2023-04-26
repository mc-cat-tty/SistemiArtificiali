# Sistemi esperti
Importanza della conoscenza specifica
#Todo 

Creazione di una base di dati (**base di conoscenza**)
1. rappresentazione della conoscenza mediante le regole -> rappresentazione **inferenziale**: se COND allora AZIONE
2. quando la base di dati contiene informazioni che soddisfano la condizione, la regola viene applicata
3. l'azione può aggiungere un nuovo elemento alla base di dati

Il **motore inferenziale** applica le regole. A forza di fare inferenze ottengo il dato che mi serve.

## Mycin
Negli anni '60 erano sistemi inferenziali che diagnosticavano malattie infettive.

La base di conoscenza è stata creata sulla base delle regole usate dai medici di Harvard. Non si parla di "allenamento", non è una rete neurale.

## Prospector
Scoperta di nuovi giacimenti

## Dendral
Analisi di composti mediante spettroscopia di massa

## R1
Configurazione dei computer DEC-Vax

I programmi tradizionali sono rigidi e difficili da mantenere. I sistemi esperti sono più naturali da comprendere, oltre che più efficaci

#Todo 

Nascono shell per motori inferenziali (anni '80)

## AI winter
Fine anni '80 - anni '90

Erano stati sottovalutati i problemi legati all'acquisizione delle conoscenze (ore e ore di domande agli esperti). Si capisce che il sistema non può superare le prestazioni degli umani che lo hanno allenato. In più si aggiunge una questione commerciale: overselling dei sistemi da parte dei venditori.

I sistemi esperti sono "mal condizionati" -> sono molto suscettibili al rumore, ovvero un dato errato porta a inferenze molto sbagliate

Il mondo dell'IA si riprende con le **reti neurali**, un altro pattern bio-ispirato più resistente al rumore dei sistemi esperti.

# Sistemi a classificatori
Una delle prime forme di apprendimento: generazione di regole sulla base delle precedenti, a differenza dei sistemi esperti.

Il modello del mondo di un classificatore si evolve mediante una pressione selettiva e grazie a meccanismi di feedback. Si interagisce con un ambiente esterno ignoto.

**Aspetti simbolici**: rappresentazione esplicita della conoscenza (a differenza dell'idea di Holland)

**Aspetti sub-simbolici**: le nuove regole vengono generate a partire dalle regole che apportano maggiore informazione al sistema (come evoluzione con selezione dei genitori)

## Architettura di un LCS - Michigan
I classificatori comunicano attraverso messaggi con effettori e detettori, i quali sono inseriti nell'ambiente ignoto.

Il classificatore cerca tra i messaggi uno che soddisfi la condizione, nel caso lo trovi esegue l'azione associata. l'azione può essere un nuovo messaggio da aggiungere alla lista della conoscenza, oppure un'azione da trasmettere agli effettori.

Holland si concetra sulle condizioni limite dei classificatori: le inferenze contraddittorie. Permette ad entrambe di esistere.

Ciclo di matching:
 1. i detettori generano messaggi
 2. il match viene tentato su tutti i classificatori e un'azione viene generata
 3. l'azione cerca il match con gli attuatori, se lo trova esegue l'azione

## Esempio
Nel modello più semplice si possono prendere come messaggi stringhe binarie.

I messaggi sono stringhe binarie, con alcuni elementi fissati.

Ad ogni messaggio è associata una variabile chiamata forza/importanza del messaggio. Dipende *anche* dal numero di volte che viene utilizzata.

La condizione è una stringa composta dai simboli $\{1, 0, \#\}$, con alcuni fissi

L'azione è una stringa composta dai simboli $\{1, 0, *\}$, con alcuni fissi

L'asterisco è il "pass through"

#Todo 

## Definizione della forza
La specificità di una regola serve a scegliere quale usare in caso di conflitto. In queste occasini si applica la più specifica.

La specificità è definita come: $\gamma = \frac{L-\gamma}{L}$ dove L è il numero di caratteri fissi nella stringa, mentre $\gamma$ è il numero di pass-through

## Ricompense
Se un classificatore esegue un'azione corretta, viene ricompensato. Distribuisce la ricompensa con tutti i classificatori da cui dipende

#Vedi: bucket brigade

## Mutazioni e crossover
Le mutazioni modificano (nell'esempio) la stringa di bit; la mutazione può introdurre qualunque simbolo. Il crossover può essere effettuato a n punti (solitamente punto singolo)

Ad ogni generazione vengono creati N figli, al ciclo dopo verranno selezionati in base alla potenza della fitness

#Todo: cover detector etc

## Parallelismo economico
Le regole sono agenti di un mercato (agenti semplici, ovvero stringhe di simboli da un alfabeto ridotto)

Si creano catene di deduzione. Grande relazione tra le regole -> interazione tra gli agenti

## Problematiche
- convergenza prematura -> non si riescono a generare nuove regole
- stringhe della stessa lunghezza
- #Todo 

## Applicazioni
- modelli ad agenti socio economici
- gaming per movimento personaggi
- simulazione di manovre aeree
- robot autonomi

