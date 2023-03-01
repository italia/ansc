## Change management

### Premessa

Il documento descrive le convenzioni di base utilizzate ogni qualvolta sia
necessario apportare modifiche software ad ANSC.

Le convenzioni che si adottano tengono conto della necessità di:

* comunicare con il minimo sforzo la risoluzione di problemi e l'introduzione
  di nuove funzionalità tra comuni, software house, e SOGEI;

* coordinare con il minimo sforzo il test di nuove versioni di ANSC tra
  comuni, software house, e SOGEI;

* garantire la compatibilità delle nuove versioni di ANSC con quelle precedenti
  per un periodo di tempo necessario per l'adeguamento dei client di stato civile.

Per far fronte a queste necessità il processo di change management introduce:

* una codifica delle versioni di ANSC che esprime l'entità dei cambiamenti
  introdotti in una nuova versione di ANSC;

* una metodologia di aggiornamento del software graduale che consente di
  testare i cliente di stato civile con le nuove versioni di ANSC e di adeguare i
  medesimi software all'evoluzione dei contratti [OpenAPI](https://swagger.io/specification/) 

* meccanismi per descrivere in modo conciso e rendere facilmente consultabili
  sia i cambiamenti introdotti in una nuova versione di ANSC che i cambiamenti
  pianificati in future versioni di ANSC.

NOTA: questo documento sostanzialmente riprende le convenzioni definite per il processo di 
	[Change management del progetto ANPR](https://github.com/italia/anpr/blob/master/src/change-management/change-management.md)
	e le adatta al contesto dello stato civile

### Codifica delle versioni

Rappresentare l'entità dei cambiamenti attraverso una codifica delle versioni
permette di comunicare in modo semplice la natura dei cambiamenti contenuti in
una nuova versione di ANSC.

La codifica delle versioni segue il [Versionamento
Semantico](http://semver.org/lang/it/). Ogni versione di ANSC viene
rappresentata da tre valori progressivi:

**MAJOR.MINOR.PATCH** (esempio: 1.4.0)

La semantica di questa codifica è la seguente:

1. Un numero di versione normale DEVE essere nella forma X.Y.Z, dove X, Y, e Z
   sono interi non negativi, e NON DEVONO contenere zeri iniziali. X è la
   versione major, Y è la versione minor, e Z è la versione patch. Ogni
   elemento DEVE incrementare come numero a sé. Per esempio: 1.9.0 -> 1.10.0 ->
   1.11.0.

2. Una volta che un pacchetto versionato è stato rilasciato, i contenuti di
   quella versione NON DEVONO essere modificati. Qualsiasi modifica DEVE essere
   rilasciata come una nuova versione.

3. La versione Patch Z (x.y.Z | x > 0) DEVE essere incrementata solo se sono
   introdotte correzioni retrocompatibili di bug. Una correzione di un bug è
   definita come una modifica interna che corregge un comportamento errato.

4. La versione Minor Y (x.Y.z | x > 0) DEVE essere incrementata se nell'API
   pubblica è introdotta una nuova funzionalità retrocompatibile. Essa DEVE
   essere incrementata se qualsiasi funzionalità dell'API pubblica è marcata
   come deprecata. Essa DEVE essere incrementata se sono introdotti all'interno
   del codice privato nuove funzionalità o miglioramenti sostanziali. Essa PUÒ
   includere modifiche di livello patch. La versione Patch DEVE essere
   reimpostata a 0 quando la versione Minor è incrementata. Esempio: La
   versione Minor viene incrementata quando si ha una nuova versione del WSDL,
   retrocompatibile con la versione precedente, che aggiunge dei campi
   opzionali, modifiche ai controlli, ulteriori metodi, o nuovi end point.

5. La versione Major X (X.y.z | X > 0) DEVE essere incrementata se nell'API
   pubblica è introdotta qualsiasi modifica non retrocompatibile. Essa PUÒ
   includere modifiche di livello minor e patch. Le versioni patch e minor
   DEVONO essere reimpostate a 0 quando la versione major è incrementata.

6. Una versione di pre-rilascio PUÒ essere indicata aggiungendo immediatamente
   dopo la versione patch un trattino e una serie di identificatori separati
   dal punto. Gli identificatori DEVONO essere composti solo da alfanumerici
   ASCII e trattini [0-9A-Za-z-]. Gli identificatori NON DEVONO essere vuoti.
   Gli identificatori numerici NON DEVONO includere zeri iniziali. Le versioni
   di pre-rilascio hanno una precedenza inferiore rispetto alla versione
   normale associata. Una versione di pre-rilascio indica che la versione è
   instabile e potrebbe non soddisfare i requisiti di compatibilità intesi come
   indicato dalla versione normale ad essa associata. Esempi: 1.0.0-alpha,
   1.0.0-alpha.1, 1.0.0-0.3.7, 1.0.0-x.7.z.92.

7. Metadati di build POSSONO essere indicati aggiungendo immediatamente dopo la
   versione patch o pre-rilascio un segno di addizione e una serie di
   identificatori separati dal punto. Gli identificatori DEVONO essere composti
   solo da alfanumerici ASCII e trattini [0-9A-Za-z-]. Gli identificatori NON
   DEVONO essere vuoti. I metadati di build dovrebbero essere ignorati nella
   determinazione della precedenza delle versione. Perciò due versioni che
   differiscono solo per i metadati di build, hanno la stessa precedenza.
   Esempi: 1.0.0-alpha+001, 1.0.0+20130313144700, 1.0.0-beta+exp.sha.5114f85.

8. La precedenza si riferisce a come le versioni sono confrontate l'una con
   l'altra quando poste in relazione d'ordine. La precedenza DEVE essere
   calcolata separando gli identificatori nell'ordine seguente: major, minor,
   patch e pre-release (i metadati di build non compaiono nella precedenza). La
   precedenza è determinata dalla prima discrepanza quando si confrontano
   ognuno di tali identificatori da sinistra a destra come segue: le versioni
   major, minor e patch sono sempre confrontate numericamente. Esempio: 1.0.0 <
   2.0.0 < 2.1.0 < 2.1.1. Quando major, minor, e patch sono uguali, una
   versione di pre-rilascio ha una precedenza inferiore rispetto alla versione
   normale. Esempio: 1.0.0-alpha < 1.0.0. La precedenza per due versioni di
   pre-rilascio con la stessa versione major, minor, e patch DEVE essere
   determinata confrontando ognuno degli identificatori separati dal punto da
   sinistra a destra finché si trova una discrepanza come segue: gli
   identificatori costituiti da sole cifre sono confrontati numericamente e gli
   identificatori con lettere o trattini sono confrontati lessicalmente secondo
   l'ordinamento ASCII. Gli identificatori numerici hanno sempre una precedenza
   più bassa rispetto agli identificatori non numerici. Un insieme più grande
   di identificatori ha una precedenza superiore rispetto a un insieme più
   piccolo, se tutti quanti i precedenti identificatori sono uguali. Esempio:
   1.0.0-alpha < 1.0.0-alpha.1 < 1.0.0-alpha.beta < 1.0.0-beta < 1.0.0-beta.2 <
   1.0.0-beta.11 < 1.0.0-rc.1 < 1.0.0.

### Classificazione delle modifiche

La codifica delle versioni appena introdotta si basa sul saper discernere quali
cambiamenti all'API pubblica del servizio devono considerarsi MINOR
(cambiamenti retrocompatibili) e quali MAJOR (cambiamenti
non-retrocompatibili).

Viene qui presentata una classificazione delle modifiche più comuni alle 
specifiche [OpenAPI](https://swagger.io/specification/) un generico servizio, 
indicando il tipo di cambiamento da esse introdotto. La
classificazione è tratta da [Web Service Contract Design and Versioning for
SOA di Thomas Erl et al](http://dl.acm.org/citation.cfm?id=1468069).

Cambiamenti retrocompatibili:

* aggiungere una nuova operazione (path) alle [OpenAPI](https://swagger.io/specification/) ed i relativi oggetti

* aggiungere un nuovo servizio con relative specifiche openapi

* aggiungere un nuovo ambiente di esposizione dei servizi

* aggiungere nuove proprietà opzionali a oggetti esistenti

* ridurre la constraint granularity di una proprietà di un oggetto delle specifiche [OpenAPI](https://swagger.io/specification/)

Cambiamenti non-retrocompatibili:

* cambiare il nome di un path esistente nelle specifiche [OpenAPI](https://swagger.io/specification/)

* rimuovere un path [OpenAPI](https://swagger.io/specification/) esistente

* aggiungere proprietà non opzionali alle specifiche [OpenAPI](https://swagger.io/specification/)

* aumentare la constraint granularity di una proprietà degli oggetti contenuti nelle specifiche [OpenAPI](https://swagger.io/specification/)

* cambiare nome ad una proprietà (opzionale o non) delle specifiche [OpenAPI](https://swagger.io/specification/)

* rimuovere una proprietà (opzionale o non) dalle specifiche [OpenAPI](https://swagger.io/specification/)


### Metodologia di aggiornamento

La metodologia di aggiornamento consente di adeguare i client di ANSC alle
nuove versioni senza interruzione di servizio.

La metodologia di aggiornamento:

* adotta una strategia per introdurre cambiamenti non-retrocompatibili
  (rilascio nuova versione MAJOR),

* stabilisce come i cliente di stato civile possano continuare ad operare durante
  l'introduzione di cambiamenti non-retrocompatibili,

* adotta un processo di testing dei client dello stato civile con le nuove versioni
  di ANSC prima che le nuove versioni raggiungano l'ambiente di produzione.

Ogni qual volta sia necessario rilasciare una nuova versione MAJOR che
introduce cambiamenti non-retrocompatibili, il servizio deve garantire la
compatibilità con la versione MAJOR precedente per almeno 90 giorni dalla messa
in produzione.

A tal fine, in tutti i path delle specifiche openapi e' presente un parametro
di percorso `version` (ad esempio  /allegato/upload/{version}) che dovrebbe 
essere usato per inviare sempre la version MAJOR richiesta per la chiamata.
Nella fase iniziale del progetto non sono state attuate politiche di controllo,
ma con il primo rilascio in ambiente di produzione, verranno accettati solo
i valori relativi alle versioni MAJOR ancora supportate.

Ogni qual volta verrà rilasciata una nuova versione MAJOR, le versioni MAJOR
precedenti non vedranno ulteriori aggiornamenti MINOR e PATCH.

Per minimizzare le interruzioni di servizio è fondamentale testare i client dello
stato civile con le nuove versioni di ANSC. Il rilascio di ogni nuova versione di
ANSC avviene in modo graduale per consentire di effettuare test di integrazione
con i cliente di stato civile di riportare problemi:

* Una nuova versione di ANSC viene rilasciata inizialmente solo ambiente di 
  preproduzione, dove vi rimane per almeno 15 giorni.

* Trascorsi i 15 giorni, se non vi sono segnalazioni aperte che riportino gravi
  problemi, la versione viene promossa alla fase di collaudo del Ministero e
  quindi in produzione.
  
* Fanno eccezioni le versioni PATCH con correzioni urgenti, che potrebbero
  essere direttamente promosse in produzione.


### Descrizione della versione

Per garantire compatibilità durante l'aggiornamento è necessario avere una
descrizione puntuale della versione corrente di ANSC, accessibile in modo
programmatico.

A tal proposito sarà possibile utilizzare il servizio `Status` per:

* richiedere la versione corrente dell'istanza di ANSC utilizzata chiamando il
  metodo `get_version`. Questo metodo ritorna la versione completa (major, minor,
  patch).

* richiedere tutte le versioni major supportate chiamando il metodo
  `get_supported_versions`.

NOTA: Le specifiche del servizio di tale servizio di `Status` verranno pubblicate
  successivamente in quanto il processo di change management è in fase di
  implementazione

Le specifiche [OpenAPI](https://swagger.io/specification/) 
  verranno pubblicate su questo repository github.

Nota: Nel caso della web application, si assume che sia associata a una
  specifica versione delle API, e verrà indicato chiaramente nelll'interfaccia.

### Storico delle versioni (ChangeLog)

Lo storico delle versioni permette di rendere facilmente consultabili i
cambiamenti introdotti da una nuova versione di ANSC. Lo storico delle versioni
viene implementato tramite [ChangeLog](docs/Changelog.md) : un file di
testo contenente un sommario dei cambiamenti presenti in ogni versione di ANSC.

È possibile consultare lo storico delle versioni all'indirizzo: [ChangeLog](docs/Changelog.md) 

Il ChangeLog viene aggiornato ogni qual volta si rilascia una nuova versione di
ANSC. Il file è diviso in varie sezioni, una sezione per versione, e le sezioni
seguono un ordine cronologico inverso per facilitare la lettura dei cambiamenti
più recenti.

Ogni sezione del ChangeLog deve contenere:

* La versione di ANSC a cui si riferisce

* La data di rilascio

* Una lista dei cambiamenti più importanti contenuti nella versione.

Se la nuova versione contiene un cambiamento relativo a una issue segnalata
nell'issue tracker, l'url della issue deve essere incluso nel sommario.

Esempio di ChangeLog ANSC:

```
## [Versione 1.4.0 - 23-01-16]
### Added
	Caso uso : Dic_Nasc_115

## [Versione 1.3.2 - 23-01-12]
### Fixed
	Regole
		- Obbligatorietà degli atti di nascita degli sposi nel matrimonio condizionata allo stato di nascita del soggetto #118293
		- Obbligatorietà dei dati sull'autorizzazione per difetto d'età nel matrimonio condizionata al tipo di difetto d'età. In particolare se vale 0, ossia nessun difetto d'età, non viene imposta. #118293
		- Obbligatorietà dei dati dell'assistente legale nel matrimonio condizionata alla presenza minori. In particolare se vale 0, ossia senza presenza minori, non viene imposta. #118293
```

### Cambiamenti Pianificati (RoadMap)

In modo analogo allo storico delle versioni, è possibile consultare anche un
file di testo contenente i cambiamenti pianificati (Roadmap). Per cambiamento
pianificato si intende qualsiasi intervento (1) cambiamento behavior
sostanziale (major/minor) e/o (2) bugfix(patch) che richiedono lunghi 
tempi per essere implementati.

È possibile consultare i cambiamenti pianificati all'indirizzo:
[Roadmap](docs/Roadmap.md) 

Lo scopo della Roadmap è duplice: da un lato permette di facilitare la
comunicazione su quando verranno introdotte nuove funzionalità, da un altro
lato facilita la stesura del file di ChangeLog al momento del rilascio di una
nuova versione di ANSC.

Anche il file di Roadmap è diviso in varie sezioni. Ogni sezione corrisponde ad
una potenziale nuova versione di ANSC, e le sezioni seguono un ordine
cronologico inverso per facilitare la lettura dei cambiamenti più recenti.

Ogni sezione della Roadmap è strutturata come il ChangeLog, con l'unica
differenza che non è obbligatorio specificare il numero di versione.

La Roadmap è particolarmente importante per comunicare quando verranno risolte
le issue segnalate nell'issue tracker, quindi anche il sommario della roadmap
dovrà includere l'url della issue segnalata.

Esempio di Roadmap ANSC:

```
# Versione ?.?.? (data stimata: 2024-12-31)

- Rimozione metodoABCD e metodoEFGH (issue:
  https://github.com/italia/ANSC/issues/AAA)

# Versione 3.?.? (data stimata: 2023-12-31)

- Aggiunta metodoXYZ per supportare casoduso123 (issue:
  https://github.com/italia/ANSC/issues/YYY)

# Versione 3.2.? (data stimata: 2023-09-30)

- Rimossa condizione di errore quando si effettua operazioneY (issue:
  https://github.com/italia/ANSC/issues/CCC)
```

