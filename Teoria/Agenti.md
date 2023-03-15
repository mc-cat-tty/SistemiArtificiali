# Syllabus
- agenti autonomi
- sistemi multiagente
- sciami di agenti

Per le simulazioni useremo Netlogo

# Significato
## Etimologia
Agency (EN):
- stato di servire come un delegato ufficiale e autorizzato
- stato di essere in azione o esercitare power (_to have free agency_)

Agentis (LAT): 
- colui che agisce per conto di altri
- da agire, fare

Cosa hanno in comune?
- uno scopo ben preciso
- delega da parte di qualcun altro
- sanno come fare -> possono stabilire autonomamente come arrivare ad un obiettivo

Altri ambiti:
- biologia -> virus
- linguistica -> nome che effettua un'azione
- microeconomia -> persona che decide in base ai propri interessi
- informatica -> user agents, management agents. Funzione che offre servizi

Caratteristiche:
- un agente sa fare una cosa in modo preciso
- diciamo all'agente *come* fare (imperativo)

## Definizione corporea
>Un agente è un'unità computazione (uno, singolare) che può essere in grado di percepire (sensori) o agire (attuatori) nel suo ambiente e ha un comportamento autonomo (deterministico, segue un algoritmo, con possibili scelte stocastiche) che almeno potenzialmente dipende dalla sua personale esperienza

Cosa non è un agente? ad esempio un braccio robotico che comando.

Tutto ciò che non è agente è Ambiente.

## Definizione sociale
>Gli agenti sono persone di società artificiali. 

TODO: finisci 

## Caratteristiche essenziali
Caratteristiche minime
- è in grado di percepire **parzialmente** il suo ambiente
- ha una rappresentazione parziale del suo ambiente (può non averne) -> modello mentale degli umani. Alcuni dettagli possono essere ignorati per velocizzare la computazione.
- è  im grado di agire nel suo ambiente
- possiede abilità e può fornire servizi

Caratteristiche aggiuntive
- guidato da tendenze (obiettivi, funzioni da ottimizzare)
- può comunicare con altri agenti (ed è particolarmente complicato)
- si può riprodurre
- il suo comportamento va verso la realizzazione dei suoi obiettivi, tenendo conto delle risorse e abilità disponibili

# Paradigmi
### Paradigma debole
L'agente è:
- **autonomo**
- **reattivo**: percepisce l'ambiente e reagisce ai suoi cambiamenti
- **pro-attivo**: comportamento diretto ad obiettivi
- **abilità sociale**: abilità di comunicare con altri agenti

>**Proattività**: provoco nell'ambiente il cambiamento che vorrei vedere

### Paradigma forte
Dentro alla definizione di _strong AI_

Vedi: test di Turing, esperimento stanza cinese

Alle cartteristiche precedenti vengono aggiunte caratteristiche ad alto livello, più umane:
- conoscenza
- intenzioni
- emozioni: intelligenza emotiva, che influenza le decisioni prese in un dato momento
- senso di obbligo
- scopi

Load balancing: un agente inizia ad evitarne un'altro, che offre servizi, nel momento in cui diventa "truffaldino" o inizia a non essere affidabile

Vedi: leggi della robotica di Asimov

Dove si colloca l'autoconservazione? l'obiettivo dell'agente potrebbe essere raggiunto attraverso l'autodistruzione

Serve una gerarchia di obiettivi. L'autoconservazione potrebbe essere un metaobiettivo -> se l'agente resta in vita può continuare a perseguire i suoi obiettivi

Spesso tendiamo ad agentizzare sistemi software, come se fossero esseri consenzienti:
- il sistema non trova il file
- il database vuole un formato differente
- ...

Questo è detto **posizione intenzionale** -> Vedi: teoria della mente di Dennett
Può essere fuorviante, perchè si crede che le azioni degli altri siano dirette verso un obiettivo

## Altri attribuiti
- mobilità: in un ambiente, come per esempio un braccio robotico
- veridicità: correttezza nel produrre informazioni, es: load balancing (perdita affidabilità in caso di bassa veridicità delle informazioni)
- benevolenza: ipotizzo che gli altri siano positivi e offro un servizio senza aver avuto in cambio nulla
- razionalità: coerenza tra azioni e obiettivi, anche se spesso la razionalità è limitata

# Architettura
Classi di agente:
- **logic-based**: la decisione è presa tramite deduzioni logiche
- **reactive**: la decisione è presa con una mappatura diretta tra situazione e azione
- **BDI - Belif-desire-intention**: la decisione dipende dalle aspettative (idee sul mondo), desideri (motivazioni interne) e intezioni (stati deliberativi).
- **layered**: la decisione è presa attraverso vari livelli, tra le quali si può saltare in base alla situazione

Comportamenti:
- **teleonomici** -> diretti verso uno scopo esplicitio (es: voglio pulire li pavimento). Teleosi = la causa/obiettivo è nel futuro.
- **riflessivi** -> lo scopo dipende dallo stato interno (es: cellule -> vogliono mantenere il proprio funzionamento)

Agenti cognitivi e reattivi:
- cognitivi: hanno una rappresentazione esplicita (simbolica) del mondo al loro interno
	- reagiscono in base alla loro rappresentazione dell'ambiente
	- TODO: finisci
- reattivi (embodied): rappresentazion sub-simbolica, non hanno una rappresentazione del mondo
	- possono reagire ad eventi
	- no piani predefiniti
	- comportamenti complessi attraverso l'interazione

Simuleremo agenti reattivi -> _swarm intelligence_