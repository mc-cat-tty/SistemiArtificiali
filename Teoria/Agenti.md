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
- **teleonomici** -> diretti verso uno scopo esplicitio (es: voglio pulire li pavimento). Teleosi = la causa/obiettivo è nel futuro. I sistemi viventi sono teleonomici.
- **riflessivi** -> lo scopo dipende dallo stato interno (es: cellule -> vogliono mantenere il proprio funzionamento)

Agenti cognitivi e reattivi:
- cognitivi: hanno una rappresentazione esplicita (simbolica) del mondo al loro interno
	- reagiscono in base alla loro rappresentazione dell'ambiente
	- TODO: finisci
- reattivi (embodied): rappresentazion sub-simbolica (no , non hanno una rappresentazione del mondo
	- possono reagire ad eventi
	- no piani predefiniti
	- comportamenti complessi attraverso l'interazione

Simuleremo agenti reattivi -> _swarm intelligence_

# Sistemi multiagente
>In informatica un sistema multi-agente è un sistema composto da numerosi agenti, in grado di instaurare interazioni reciproche (comunicazione bidirezionale o percezione/modifica dell'ambiente). L'interazione può essere sotto forma di scambio di messaggi o modifica dell'ambiente comune.

Lasciare segnali nell'ambiente comune per dare indicazioni (cambiare il comportamento di altri agenti) è chiamata **stigmergia**: https://en.wikipedia.org/wiki/Stigmergy

I gruppi di agenti si possono anche sciogliere se manca l'interazione.

I singoli agenti sono **limitati**: ha limiti nella quantità di conoscenza che può acquisire/processare nel tempo, risorse limitate, tempo limitato

## Distribuzione
Molti problemi sono intrinsicamente distribuiti, come la ricerca in vaste zone.

Può occorrere concentrare più agenti in luoghi maggiormente densi di informazione: i ricercatori si concentrano dove l'asticella non affonda, mappatura sui contorni di un'immagine.

Gli agenti sono **specializzati**, ognuno ha un compito specifico. Gli agenti general-purpose sono lenti e inefficienti.

Viviamo in un mondo di agenti: ogni agente è specializzato e ha obiettivi/interessi differenti dagli altri.

Molti sistemi informatici nascono come sistemi multiagente:
- componenti distribuiti: sensori, repliche, sistemi mobili, ...
- interagenti attraverso la rete: p2p, pervasive computing
- situati in uno stesso ambiente: fornisce lo scopo comune

## Controllo di processo
È uno dei primi ambiti dove sono stati introdotti agenti intercomunicanti.

Un agente per ogni stage del processo produttivo (stadio di lavorazione).

- industria per controllare la produzione dei beni di consumo
- ambienti domestici
- start cities: controllo del traffico

## Gestione risorse
Gestione del carico sulle celle della rete cellulare:
- un criterio potrebbe seguire il modello economico
- più celle entrano in competizione quando una chiamata deve essere avviata

Reti elettriche:
- load balancing tra le centrali elettriche

Reti di computer:
- reti di server per la memorizzazione
- vedi CERN di Ginevra

## Workflow management
1. assigments
2. teleworkers
3. portal
4. documents
5. storage (archive)
6. ...

# Simulazioni
Il traffico stradale è stato simulato per anni come sistema idraulico (**modello idrodinamico**):
- macchine -> particelle, diverse dagli scooter che possono passare in ogni caso
- semafori -> valvole
- incidente -> intoppo

Fun fact: i modelli usati per simulare il traffico stradale tra Germania e Italia sono differenti. Gli agenti si comportano diversamente nei due paesi, le simulazioni producono un diverso numero di incidenti, per abbassarne il valore in Italia il limite è più restrittivo.

Le situazioni di panico nelle società umane (fuga da edifici, navi, ecc.); altri esempi sono epidemie, scenari economici, ecc.

Anche nell'industria dell'intrattenimento vengono usate simulazioni del genere:
- batman begins (pipistrelli)
- non playing characters

## Ottimizzazione
Molti algoritmi di ottimizzazione

Vedi: particle swarm optimization, ant per selezione del shortest path

# Swarm intelligence
>Proprietà di un sistema il cui comportamento collettivo degli agenti (in grado di interagire localmente con l'ambiente) fa emergere pattern funzionali globali nel sistema. Gli agenti di questo sistema sono spesso non sofisticati (le formiche hanno una manciata di neuroni).

Api che si coordinano in modo intelligente, senza avere un capogruppo; l'ape regina è specializzata solo nella produzione di uova.

Le formiche, collettivamente, risolvono un complesso problema logistico, quando devono cercare di portare il latte alle larve.

L'intelligenza collettiva non è la somma delle intelligenze dei singoli agenti.

## Sistemi che esibiscono swarm intelligence
- il cervello umano: sciame di neuroni, che sono semplici sommatori a soglia
- colinie di animali, insetti e batteri
- cellule: derivano dall'interazione delle proteine

Per riassumere, sono tutti sistemi robusti al rumore e alle variazione dell'ambiente. Sono basati su feedback loop.

## Emergenza
I comportamenti della swarm intelligence sono detti **emergenti**, in quanto **emergono** dalle interazioni degli agenti, che prendono decisioni stupide per soddisfare il loro interesse.

L'emergenza del sistema si nota dall'esterno (agli occhi dell'osservatore)

Vedi: flocking model (flock = stormo, gregge)