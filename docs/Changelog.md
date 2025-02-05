# Changelog 

Changelog per i file che definiscono modelli e interfacce con i sistemi di terze parti. 

Inserire qui versione della modifica e tipo della modifica. Il tipo della modifica indica l'operazione fatta sui file e può essere una o più delle possibili azioni **Added** (per informazioni aggiunte), **Changed** (per informazioni esistenti modificate), **Fixed** (per correzione di errori), **Deprecated** (per eventuali dati e/o servizi non più correnti), **Removed** (per la rimozione di file o dati).

Usare la sintassi mark down 

Categorizzare le modifiche secondo le seguenti voci:

- **model_evento.yaml** se le modifiche sono sul modello dati
- **[Nome yaml servizio]** se le modifiche sono specifiche di un servizio cooperativo
- **Web Application** se le modifiche sono specifiche della web application
- **Processo** se le modifiche si riferiscono al processo del sistema e ha impatti sia lato servizi cooperativi che web app
- **Decodifica** se le modifiche si riferiscono ai valori degli elementi indicati da codici
- **Regole** se le modifiche si riferiscono a una o più regole di validazione

I nuovi dati vanno sempre inseriti in testa in modo che le prime righe siano relative all'ultima modifica.

NOTE:
~~- Per verificare le differenze tra~~ due versioni di questo repository, è possibile usare anche gli strumenti di comparazione messi a disposizione da git, in particolare l'interfaccia web di github, ad esempio [Questa è la comparazione tra il tag v1.19.0 e il tag v1.20.0](https://github.com/italia/ansc/compare/v1.19.0...v1.20.0) 
- Inoltre per l'elenco delle principali modifiche apportate specificatamente al mapping dei casi d'uso, è presente un [changelog dedicato](Mapping_casi_uso/changelog_mapping.md).

## [Unreleased]

## [1.37.1 - 05-02-2025]

### Fixed

- Corretto campo da siglaEnunciazioni a siglaEnunciazione nell'openapi R019 <https://github.com/italia/ansc/issues/1291>

## [1.37.0 - 04-02-2025]

### Added

- [versione] Aggiunta versione 100020
- [feature] Per tutti gli atti digitali riportare nella composizione e nelle certificazioni "atto presente nell’Archivio Nazionale informatizzato dei registri dello Stato Civile dal comune XY"  (ID 143)
- [webapp]: Gestione tipologie certificati emissibili per caso d'uso di servizio (ID 167)
- [feature] Gestione estremi atto cartacei (aggiunta volume) (ID 141)
- [feature] Adozione estera legittimante richiesta da consolato <https://github.com/italia/ansc/issues/1254> (ID 176)
- [feature] Consultazione/certificazione da parte delle prefetture (ID 140)
- [feature] Gestione degli allegati errati (ID 166)

- [model_evento.yaml]
  - Aggiunto il campo volume in ModelAttoCollegato

### Fixed

- [SC]: 12222123 Riconoscimento materno di figlio di ignoti ultraquattordicenne Rico_008  <https://github.com/italia/ansc/discussions/1267>
- [webapp]: RICHIESTA FIRMA DICHIARANTE PER TRASCRIZIONE ATTI MULTIPLI CITTADINANZA <https://github.com/italia/ansc/discussions/1270>
- [SC]: Anteprima - Matrimonio: ordine dei firmatari in calce all'atto <https://github.com/italia/ansc/issues/1217> <https://github.com/italia/ansc/issues/809>
- [SC]: Estratto per riassunto e annotazioni di riconoscimento <https://github.com/italia/ansc/issues/1125> <https://github.com/italia/ansc/issues/1210>
- [WA] Caso d'uso 11315000 - Dichiarazione di nascita non riconosciuta: corretta composizione atto
- Gestione allegati che rimangono in stato in elaborazione per un tempo eccessivo
- [SC]: Validazione Use Case 1363 <https://github.com/italia/ansc/issues/1034>
- Annotazione su Comunicazione di Consolato - Dati Ente Dichiarante (cdu 14500000) (ID 163) <https://github.com/italia/ansc/issues/1214>
- [Web App] - Errata gestione ricerca soggetto per Identificativo unico nazionale
- [webapp]: Obbligatorietà dati nascita nel caso acquisto cittadinanza art.14 L.91/1992 <https://github.com/italia/ansc/issues/1229>
- [SC]: usecase 11411010 - Dichiarazione fuori del matrimonio nei termini di legge resa dal padre, di bimbo riconosciuto da entrambi i genitori prima della nascita <https://github.com/italia/ansc/issues/1268>
- caso d'uso 12211312  Riconoscimento paterno di nascituro gia' riconosciuto dalla madre  <https://github.com/italia/ansc/issues/1269>
- Difficoltà nell'applicare la firma ARUBA dell'Ufficiale di Stato Civile <https://github.com/italia/ansc/issues/1281>
- [SC]: Firma USC - Errore "USC dell'operazione di firma diverso da chi ha firmato l'attestazione" <https://github.com/italia/ansc/issues/1279>
- Annotazione errore materiale: servizio di firma usc invocato errato
- [SC]: Firma Remota non Avvenuta con Successo- Annotazione <https://github.com/italia/ansc/issues/1275>
- Consultazione provvedimenti di rifiuto (da web app e servizi)
- [R002] caso d'uso 12211312  Riconoscimento paterno di nascituro gia' riconosciuto dalla madre  <https://github.com/italia/ansc/issues/1269>


## [1.36.7 - 23-01-2025]

### Fixed

- [SC]: Errata indicazione del campo id Ansc <https://github.com/italia/ansc/discussions/1264>

## [1.36.6 - 23-01-2025]

### Fixed

- tabella ansc_3  : corretto tipo contenuto per caso d'uso 459200 <https://github.com/italia/ansc/discussions/1190>
- ansc_064 non aggiornata : aggiunta la decodifica mancante <https://github.com/italia/ansc/discussions/1137>

## [1.36.5 - 22-01-2025]

### Fixed

- [SC]: versione 1.36.3 tabella ansc_20 - aggiunto valore 3 a tabella decodifica 20 <https://github.com/italia/ansc/issues/1261>
- Correzione annotazione: corretto errore 500 <https://github.com/italia/ansc/issues/1000>
- [SC] R015: Corretto errore Dati mancanti nuove generalita sull'atto di adozione nuovoNome nuovoCognome <https://github.com/italia/ansc/issues/1253>


## [1.36.4 - 17-01-2025]

### Fixed

- [1.2.2.2.2.2.0.3] Riconoscimento materno di figlio di ignoti infraquattordicenne: corretto allegato obbligatorio errato <https://github.com/italia/ansc/issues/1248>
- [SC]: casistica 12224123 Riconoscimento di figlio di ignoti ultraquattordicenne da parte del padre con presenza della madre (Rico_011): corretto allegato errato <https://github.com/italia/ansc/issues/1249>
- [SC]: Corretto problema consultazione ANSC intestatario <https://github.com/italia/ansc/issues/1245>
- Annotazioni per errore materiale e rettificative: correzione validazione evento

## [1.36.3 - 15-01-2025]

### Added

- [decodifiche] Aggiunto valore in decodifica ANSC_20 dec_ente_documento_riconoscimento: 3 - "Altra autorità straniera"

### Fixed

- Data certificati: corretto formato data emissione 
- [SC]: Ricerca soggetto per intestatario e comune estero di nascita <https://github.com/italia/ansc/issues/1232>
- [webapp]: Straniero nato in italia che vi abbia risieduto legalmente senza interruzioni fino alla maggiore eta' <https://github.com/italia/ansc/issues/1237>
- [SC]: firma attestazione di Conformità - impedire caricamento tipo allega 99
- [SC]: firma attestazione di Conformità - verifica tipi allegati per tipo evento in base a configurazione
- [SC]: problema con caso uso 12221122 <https://github.com/italia/ansc/issues/1235> (adeguato messaggio, rimosso controllo di maggiore età)
- [SC]: R005 il tag idComuneRegistrazione ritorna il codice istat invece che l'ID <https://github.com/italia/ansc/issues/1246>
- [webapp]: Notifiche divorzio art.6 D.L. n. 132/2014 <https://github.com/italia/ansc/issues/1238>
- [SC]: Mancanza Notifiche a seguito nullità matrimonio <https://github.com/italia/ansc/issues/1228>
- [webapp]: aggiornato flusso distribuzione chiavette
- [SC]: aggiornamento di idComuneRegistrazione quando ritorna codice ISTA invece che id

## [1.36.2 - 09-01-2025]

### Fixed

- model_evento.yaml non allineato alla release 1.36.0 <https://github.com/italia/ansc/issues/1234>

- Sistemata documentazione:
  - [R019_certificato_internazionale.yaml] 
    - CertificatoNascitaDTO sostituiti i campi annotazione e siglaEnunciazioni con listaEnunciazioni
    - CertificatoMatrimonioDTO sostituiti i campi annotazione e siglaEnunciazioni con listaEnunciazioni
    - AnnotazioneEventoResponse modificato il tipo del campo listaAnnotazioni da ModelEvento a InfoAnnotazione

  - [model_evento.yaml] 
    - Aggiunti i campi:
      - dataPubblicazioneSentenza e dataDecorrenzaSentenza in ModelTrascrizioneSeparazione

## [1.36.1 - 30-12-2024]

### Fixed

- [SC]: Anteprima caso uso 1364 - Dati in ingresso non corretti <https://github.com/italia/ansc/issues/1218>
- [SC]: Certificazione e Estratti per Copia Integrale <https://github.com/italia/ansc/issues/1219>

## [1.36.0 - 23-12-2024]

### Added

- [versione] Aggiunta versione 100019
- [feature] Annotazione modificativa per cambio sesso (ID 95.a)
- [feature] Servizi di collegamento con PA digitale (controlli da effettuare per l’approvazione del contributo) (ID 43.b)
- [feature] Gestione giuramento cittadinanza con firma sindaco in differita (ID 135)
- [feature] DM Nascita e Morte (ID 117): funzionalità disponibile solo in ambiente di pre produzione
- [feature] Completamento funzionalità per il  Comune relative al rilascio certificazioni per servizi al cittadino (flusso richiesta estratti) (ID110): funzionalità disponibile solo in ambiente di pre produzione

- [casi d'uso] Aggiunto nuovo caso d'uso [1.4.8.7.0.0.0.0] (Dic_Nasc_998_8) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE (Annotazione modificativa per cambio sesso)

- [decodifiche] Aggiunto valore in tipo allegato decodifica ANSC_9 DEC_TIPO_ALLEGATO: 109 certificato di cui all’art.36 del Regolamento (UE) N. 2019/1111

- [R019_certificato_internazionale.yaml] Modificati:
  - CertificatoNascitaDTO sostituiti i campi annotazione e siglaEnunciazioni con listaEnunciazioni
  - CertificatoMatrimonioDTO sostituiti i campi annotazione e siglaEnunciazioni con listaEnunciazioni
  - AnnotazioneEventoResponse modificato il tipo del campo listaAnnotazioni da ModelEvento a InfoAnnotazione
  
- [model_evento.yaml]
  - Aggiunti i campi:
    - dataPubblicazioneSentenza e dataDecorrenzaSentenza in ModelTrascrizioneSeparazione

### Fixed

- [R019] - Modifica logica enunciazioni <https://github.com/italia/ansc/issues/1156>
- [R019] - Fix luogo matrimonio (dentro la casa comunale) e modifica logica cognome dopo il matrimonio <https://github.com/italia/ansc/issues/1160>
- [SC]: Rilascio certificazione come copia integrale dell'atto - errore interno in risposta <https://github.com/italia/ansc/issues/1180>
- [SC]: Ordine firmatari atto unione civile - caso d'uso 411111 <https://github.com/italia/ansc/issues/1182>
- [webapp]: caso d'uso 347000 trascrizione di una sentenza di divorzio da consolato <https://github.com/italia/ansc/issues/1126>
- [SC]: Obbligatorietà che non dovrebbe essere richiesta per il caso d'uso Rico_007 (12222121) <https://github.com/italia/ansc/issues/1146>
- [SC] Annotazione Rettifica - corretta NullPointer Exception
- [WA] CASO USO MORTE: corretta minuta atto
- Ordinamento su Consultazione notifiche <https://github.com/italia/ansc/discussions/1186>
- [SC]: Assenza degli estremi dell'Atto, nell'Annotazione automatica (caso d'uso 52143: Citt_004) <https://github.com/italia/ansc/issues/1187>
- [SC]: CASO D'USO 347000 TRASCRIZIONE SENTENZA DIVORZIO DALL'ESTERO - allegati mancanti <https://github.com/italia/ansc/issues/1203>
- Unione civile fuori casa comunale- FORM. 121.1 (ID 73 Consorzio Bolzano)
- [webapp]: Notifica annotazione divorzio estero su atto matrimonio <https://github.com/italia/ansc/issues/1205> 
- [webapp]: testo annotazione matrimonio F.132 su atto nascita <https://github.com/italia/ansc/issues/1206>
- Allegati al caso uso 1324 (Trascr_010) <https://github.com/italia/ansc/discussions/1200>
- ID109: indicazione esplicita delle tipologie di certificazione emissibili nei casi d’uso di servizio
- Corretta tabella decodifica ansc_3 <https://github.com/italia/ansc/discussions/1138>
- Corretto errore nella registrazione di un atto: salvataggio di un soggetto intestatario con eventi già collegati
- [SC]: casistica unciv_003 allegato mancante <https://github.com/italia/ansc/issues/1209>

## [1.35.3 - 12-12-2024]

### Fixed

- Corretto errore nel salvataggio dati di dettaglio  <https://github.com/italia/ansc/issues/1171> <https://github.com/italia/ansc/issues/1185>

## [1.35.2 - 09-12-2024]

### Fixed

- Corretta generazione notifiche anagrafiche per soggetti nati all'estero <https://github.com/italia/ansc/issues/1194>

  
## [1.35.1 - 05-12-2024]

### Fixed

- Flusso di distribuzione delle chiavette OTP da parte delle prefetture: corretta ricerca del delegato
- corretta la redirect url di conferma email nella funzione di richiesta firma remota da parte dell'USC
- Visualizzazione atto in errore: Generic error <https://github.com/italia/ansc/issues/1148>
- [webapp] UC 3.6.9.0.0.0 Annotazione modificativa generica: corretta anomalia presente nella sezione soggetto collegato <https://github.com/italia/ansc/issues/1134>

## [1.35.0 - 02-12-2024]

## Added

- [feature] Disabilitazione nota tecnica #151163
- [feature] Trascrizione del decreto prefettizio di cambiamento del nome e cognome pervenuta da consolato (ID 115)
- [feature] Estratto per copia integrale semplificato (ID 121)
- [feature] Adeguamento casi d'uso nascita con pre riconoscimento paterno (ID 122)
- [feature] Dichiarazioni di nascita con luogo redazione diverso dalla casa comunale (ID 123)
- [feature] Trascrizione decreto prefettizio cambio cognome per più intestatari (ID 136)
- [feature] Annotazione su atti nascita in seguito a trascrizione sentenze di adozione con multiintestatari (ID 137)
- [feature] Unioni civili gestione legge patrimoniale e certificati #1002 (ID 133)
- [feature] Aggiornamento certificati lato servizi al cittadino 
- [feature] Gestione flusso di rilascio chiavette da parte delle prefetture (ID 138)
- [feature] Completamento dei casi d’uso in multilingua e adeguamento al multilinguismo delle funzionalità (ID20.b)
- [feature] Adeguamento ai fini della conservazione della nota tecnica (ID118)

- [R002_certificazione.yaml] Aggiunto flagSemplificato nel payload per ottenere il certificato estratto per copia integrale semplificato ossia senza metadati (per ID 121)
- [R020_adozione_muli_intestatario.yaml] Aggiunto il servizio per la validazione delle Annotazioni su atti nascita in seguito a trascrizione sentenze di adozione con multiintestatari (per ID 137)
- [model_evento.yaml]
  - Aggiunti i campi:
    - datiAdozioneMultiIntestatario di tipo ModelAdozioneMultiIntestatario (per ID 137)
    - flagRichiestaPerPosta di tipo boolean in ModelTrascrizioneCittadinanza
    - protocollo e dataVerbale di tipo string in ModelDatiEventoCittadinanza 
    - dataRedazione, oraRedazione, minutiRedazione di tipo string in ModelDatiDiNascita (per ID 123)
  - Riabilitazione di un campo deprecato:
    - ufficialeStatoCivile di tipo ModelSoggetto


- [versione] Aggiunta versione 100018
- [casi d'uso] Aggiunto nuovo caso d'uso [1.3.3.2] (Trascr_031) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [casi d'uso] Aggiunto nuovo caso d'uso [1.3.3.3] (Trascr_032) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [casi d'uso] Aggiunto nuovo caso d'uso [1.4.9.6.0.0.0.0] (Dic_Nasc_998_6) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [casi d'uso] Aggiunto nuovo caso d'uso [1.4.9.7.0.0.0.0] (Dic_Nasc_998_7) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [casi d'uso] Aggiunto nuovo caso d'uso [4.5.9.2.0.0] (UnCiv_998_5) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [casi d'uso] Aggiunto nuovo caso d'uso [1.3.5.5] (Trascr_030) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [decodifiche] Aggiunto valore in tipo allegato decodifica ANSC_9 DEC_TIPO_ALLEGATO: 108 = Negoziazione assistita e nulla osta o autorizzazione
- [decodifiche] Aggiunta decodifica ANSC_118 DEC_TIPO_ADOZIONE per campo tipoAdozione (ID 137)
- [decodifiche] Aggiunta decodifica ANSC_119 DEC_TIPO_FORMULA_SECRETATO per Tipologia di formula Annotazione Adozione Multipla NON Secretata (ID 137)
- [decodifiche] Aggiunta decodifica ANSC_120 DEC_TIPO_FORMULA_NON_SECRETATO per Tipologia di formula Annotazione Adozione Multipla Secretato (ID 137)

### Fixed

- Annotazione di separazione personale dei coniugi
- Notifiche non generate a seguito di evento conferma accordo di separazione o divorzio <https://github.com/italia/ansc/issues/1155> <https://github.com/italia/ansc/issues/1157>
- [webapp]: Notifiche divorzio art.6 D.L. n. 132/2014 <https://github.com/italia/ansc/issues/1151>
- ID 133:Unioni civili gestione legge patrimoniale e certificati <https://github.com/italia/ansc/issues/1002>
- Errore in composizione in caso di decreto acquisto di cittadinanza #1142 <https://github.com/italia/ansc/issues/1142>
- Caso d’uso negoziazione assistita: allegato obbligatorio: NOME ALLEGATI CASO D'USO 345000 <https://github.com/italia/ansc/issues/1143>
- Nuovo caso d'uso : Trascrizione del provvedimento straniero di adozione di minore riconosciuto valido dal tribunale dei minori fuori convenzione Aja <https://github.com/italia/ansc/issues/1039>
- Provvedimento di adozione estera: reso opzionale allegato atto di nascita
- Data annotazione negli estratti per riassunto: da eliminare
- caso d'uso 52143 figlio minore di chi ha acquistato la cittadinanza: aggiunto allegato atto di nascita figlio
- [SC]: Ricerca intestatario: incongruenza campo comune nascita estero <https://github.com/italia/ansc/issues/1169>
- caso d'uso 1342 - TRASCRIZIONE SENTENZA DI ADOZIONE IN CASI PARTICOLARI <https://github.com/italia/ansc/issues/1138> <https://github.com/italia/ansc/issues/1149>
- Annotazione automatica generata a seguito di scelta cambio cognome
- Matrimonio con rito civile nella casa comunale  con impedimento di uno degli sposi
- [SC]: Tipo accertamento "dichiarazione sostitutiva" non sempre consentito <https://github.com/italia/ansc/issues/1159>
- Trascrizione di adozione dall'estero: dati provvedimento di origine (Trascr_018 - Trascr_020) <https://github.com/italia/ansc/issues/1168>
- [R009] - Errore interno: aggiornamento atto confermato tramite R009 <https://github.com/italia/ansc/issues/1167>
- Emissione certificati possibile per atti non in stato conclusivo <https://github.com/italia/ansc/issues/1178>
- Modifica link guida adesione ANSC - il link alla guida di adesione nella pagina di amministrazione ora fa riferimento al portale ANPR
- Verifica formato file incapsulati nei p7m : i file firmati p7m (id tipo 4) devono essere di uno degli altri tipi consentiti
- [SC]: cambiamento del nome e cognome a seguito di notifica ANSC <https://github.com/italia/ansc/issues/1172>
- [WA] Matrimonio con rito civile nella casa comunale  con impedimento di uno degli sposi: corretta minuta <https://github.com/italia/ansc/issues/1175>
- UC Annotazione per correzione per articolo 98 di atto di morte: da estendere per comprendere la modifica dello stato civile <https://github.com/italia/ansc/issues/1116>
- Data annotazione negli estratti per riassunto: eliminata
- Modulo per presa visione nell'applicazione per la firma digitale del dichiarante: mancano alcuni dati <https://github.com/italia/ansc/issues/1087>

## [1.34.7 - 21-11-2024]

### Fixed

- [SC]: "descrizioneLocalita" estera in notifica ANPR <https://github.com/italia/ansc/issues/1162>
- Caso dep_div_001: per i coniugi oltre al nome e cognome aggiungere data di nascita e luogo di nascita (formula 121.ter)
- Matrimoni/Unione civile (officiante) rito civile: frase iniziale della composizione - trasversale <https://github.com/italia/ansc/issues/1129>
- [WA]: Cittadinanza Straniero nato in Italia che vi abbia risieduto legalmente senza interruzioni fino alla maggiore eta': corretta composizione
- Multilinguismo: aggiornamento casi d'uso Riconoscimento (ID135,ID136)
- Multilinguismo: aggiornamento casi d'uso separazione-divorzio (ID114.h,ID114.f,id114.h,id114.a)
- Multilinguismo: aggiornamento casi d'uso matrimonio (ID10.d,ID114.f,id114.h,id114.a,ID10.b,ID10.c)
- Multilinguismo: aggiornamento casi d'uso matrimonio-riconciliazioni (ID77)
- Multilinguismo: aggiornamento casi d'uso dichiarazioni di nascita (ID119)
- Multilinguismo: aggiornamento casi d'uso morte (ID129,ID133,ID80,ID128)
- Multilinguismo: aggiornamento casi d'uso cittadinanza (ID50)
- Multilinguismo: aggiornamento casi d'uso trascrizione matrimonio (ID78)
- Multilinguismo: aggiornamento casi d'uso Unione Civile (ID5,Id11,ID75)

## [1.34.6 - 19-11-2024]

### Fixed

- Utente ministero / DTD : Visualizzazione data chiusura registro

## [1.34.5 - 18-11-2024]

### Fixed

- Adozione casi particolari: correzione caso d'uso 1342 <https://github.com/italia/ansc/issues/1149>
- Estatto riassunto: correzione relativa allo stato nascita estero <https://github.com/italia/ansc/issues/1154>
- Controllo bloccante per annotazioni apposte su atti digitali formati da altro comune <https://github.com/italia/ansc/issues/1153>
- Monitoraggio cruscotto di adesione: ordinamento lista dei record restituiti 
- Monitoraggio adesione: data chiusura registri vuota con - per i comuni che hanno solo proposto di aderire
- Trasversale: eliminare il menu Amministrazione se non compaiono funzioni visibili per il ruolo dell'utente loggato 

## [1.34.4 - 15-11-2024]

### Fixed

- [SC]: Firma USC per Rettifiche - Firma non avvenuta con successo. <https://github.com/italia/ansc/issues/1070>

## [1.34.3 - 14-11-2024]

### Fixed

- [SC]: R013 Validazione Rettifica Erroire Materiale: dati soggetto intestatario non conformi: <https://github.com/italia/ansc/issues/1147>
- Utente ministero DTD : Correzione ricerca comuni cruscotto adesione ANSC

## [1.34.2 - 11-11-2024]

### Fixed

- [SC]: R002 Certificazione: Trascrizione matrimonio celebrato all'estero, corretto errore bloccante
- [WA]: Adozione artt. 25-27 Legge n. 183/1984 (annotazione F.122) #1141 <https://github.com/italia/ansc/issues/1141>
- [SC]: R010 Anteprima per presa visione: corretta tipologia di firma online/cartacea
- [webapp]: Procedura di Proposta Adesione ANSC <https://github.com/italia/ansc/issues/1140>

## [1.34.1 - 06-11-2024]

### Fixed

- [SC]: Corretti certificati unioni civili per condizione patrimoniale comunione dei beni <https://github.com/italia/ansc/issues/1117>
- [SC]: Trascrizione matrimonio celebrato all'estero - reso opzionale luogo nascita sposi - errore bloccante (UC 331000) <https://github.com/italia/ansc/issues/1127>
- [WA] Cruscotti di adesione: corretto controllo data di dichiarazione di adesione
- [SC]: versione 1.34 caso d'uso 2214 <https://github.com/italia/ansc/issues/1132>

### Fixed Multilinguismo

- Multilinguismo - Matrimonio ID 10
- Multilinguismo Sep-Div  ID 79 (già corretta)
- Multilinguismo - trasversale ID 5
- Multilinguismo Unione civile TD 38 (già corretto)
- Multilinguismo Dic. Nasc ID 68
- Multilinguismo - Dic Nasc ID 70
- Multilinguismo Unione civile ID 76
- Multilinguismo - scioglimento unione civile ID 81
- Multilinguismo - atti trascritti ID 82
- Multilinguismo - dichiarazione nascita ID 99 
- Multilinguismo dichiarazione nascita ID 101
- Multilinguismo Unione civile in imminente pericolo di vita

## [1.34.0 - 04-11-2024]

### Added

- [feature]  Dichiarazione entro i 10 giorni resa dal procuratore del padre – filiazione fuori dal matrimonio con il consenso della madre ad essere nominata, con consenso contestuale (ID107)
- [feature]  Restituzione formula utilizzata nelle annotazioni automatiche <https://github.com/italia/ansc/issues/1122> (ID127)
- [feature]  Gestione firmatari (impedimenti, comprensione) (ID37)
- [feature]  Trascrizione atti multipli registro cittadinanza (ID114)
- [feature]  Trascrizione atti multipli adozioni (ID114.a)
- [feature]  Indicazione esplicita delle tipologie di certificazione emissibili nei casi d’uso di servizio (ID109)
- [feature]  Sezione di monitoraggio: consultazione online riepilogativa delle proposte di adesione ad ANSC da parte dei comuni (ID131)

- [versione] Aggiunta versione 100017
- [decodifiche] Aggiunta decodifica ANSC_116 DEC_TIPO_ADOZIONE per campo tipoAdozione (ID 114 e ID 114.a1)
- [casi d'uso] Aggiunto nuovo caso d'uso [1.1.2.1.8.0.0.0] (Dic_Nasc_121) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [casi d'uso] Aggiunto nuovo caso d'uso [1.1.2.1.8.1.0.0] (Dic_Nasc_122) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [casi d'uso] Aggiunto nuovo caso d'uso [1.1.2.1.8.2.0.0] (Dic_Nasc_123) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [casi d'uso] Aggiunto nuovo caso d'uso [1.1.2.1.9.0.0.0] (Dic_Nasc_124) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [casi d'uso] Aggiunto nuovo caso d'uso [1.1.2.1.9.1.0.0] (Dic_Nasc_125) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [casi d'uso] Aggiunto nuovo caso d'uso [1.1.2.1.9.2.0.0] (Dic_Nasc_126) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [casi d'uso] Aggiunto nuovo caso d'uso [1.1.2.2.8.0.0.0] (Dic_Nasc_127) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [casi d'uso] Aggiunto nuovo caso d'uso [1.1.2.2.8.1.0.0] (Dic_Nasc_128) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [casi d'uso] Aggiunto nuovo caso d'uso [1.1.2.2.8.2.0.0] (Dic_Nasc_129) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [casi d'uso] Aggiunto nuovo caso d'uso [1.1.2.2.9.0.0.0] (Dic_Nasc_130) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [casi d'uso] Aggiunto nuovo caso d'uso [1.1.2.2.9.1.0.0] (Dic_Nasc_131) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [casi d'uso] Aggiunto nuovo caso d'uso [1.1.2.2.9.2.0.0] (Dic_Nasc_132) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [casi d'uso] Aggiunto nuovo caso d'uso [1.1.2.1.1.2.0.4] (Dic_Nasc_133) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [casi d'uso] Aggiunto nuovo caso d'uso [1.3.8.1] (Trascr_028) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [casi d'uso] Aggiunto nuovo caso d'uso [1.3.8.2] (Trascr_029) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [casi d'uso] Aggiunto nuovo caso d'uso [5.2.8.2.1] (Citt_049) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [decodifiche] Aggiunto valore in tipo allegato decodifica ANSC_9 DEC_TIPO_ALLEGATO: 106 = Documenti utilizzati per la pubblicazione
- [decodifiche] Aggiunto valore in tipo allegato decodifica ANSC_9 DEC_TIPO_ALLEGATO: 107 = Certificato medico
- [decodifiche] Aggiunto valore in tipo richiedente decodifica ANSC_64 DEC_TIPO_RICHIEDENTE: 5 = Madre e Padre

- [model_evento.yaml]
  - Aggiunto il campo:
    - richiedente di tipo ModelRichiedente (per ID 114 e ID 114.a1)
    - flagCertificatoSemplice (Indica se il caso d'uso di servizio è abilitato ad emettere il certificato semplice (true=ABILITATO, false=NON ABILITATO))
    - flagEstrattoPerRiassunto (Indica se il caso d'uso di servizio è abilitato ad emettere l'estratto per riassunto (true=ABILITATO, false=NON ABILITATO))
    - tipoAdozione (Tipo adozione (decodifica ANSC_116)) in ModelTrascrizioneNascita


### Fixed

- [SC]: allegati relativi alle pubblicazioni negli negli atti di matrimonio <https://github.com/italia/ansc/issues/997>
- Atti morte: gestito stato civile del defunto ignoto
- Trascrizione decreto prefettizio cambio cognome/nome: aggiunta possibilità di selezionare entrrambi i genitori come richiedenti
- [SC]: Errore Validazione caso d'uso 51102 <https://github.com/italia/ansc/issues/1100>
- Caso d'uso di nascita mancante, per una delle combinazioni, per bimbo nato vivo ma morto prima della denuncia di nascita <https://github.com/italia/ansc/discussions/1020>
- [SC]: R002 - Errore Servizio certificazione: "Tipo di certificato non valido con uso matrimonio <https://github.com/italia/ansc/issues/1109>
- Matrimonio in imminente pericolo di vita: aggiunta allegato <https://github.com/italia/ansc/issues/1121>
- Matrimonio in imminente pericolo di vita - Accertamento volontà non digitabile <https://github.com/italia/ansc/issues/1110>
- [SC]: impossibile creazione atto di morte (Morte_001): esteso controllo bloccante su idANPR <https://github.com/italia/ansc/issues/1111>	
- Negoziazione assistita: ricerca avvocati <https://github.com/italia/ansc/issues/710>
- [SC]: Mancanza dati in risposta consultazione ansc intestatario <https://github.com/italia/ansc/issues/1098>
- Caso d'uso di nascita mancante, per una delle combinazioni, per bimbo nato vivo ma morto prima della denuncia di nascita <https://github.com/italia/ansc/issues/1106> <https://github.com/italia/ansc/issues/1020>
- [SC] Annotazioni automatiche - richiesta nuovi campi nella risposta <https://github.com/italia/ansc/issues/1122> <https://github.com/italia/ansc/issues/836>
- Correzione estratto integrale matrimonio: corretta data trasmissione


## [1.33.5 - 28-10-2024]

## Changed

- [Guida adesione ANSC](https://www.anagrafenazionale.interno.it/wp-content/uploads/Guida-operativa-per-adesione-ad-ANSC.pdf) link a portale ANPR.

## [1.33.4 - 24-10-2024]

### Changed

- Aggiornata la guida operativa della web app (in particolare aggiunta una sezione per l'applicazione di generazione dell'otp).

### Fixed

- [SC]: Cittadinanza - Notifiche ANPR che arrivano tramite web-service <https://github.com/italia/ansc/issues/1104>

## [1.33.3 - 17-10-2024]

### Fixed

- [SC]: Metadati mancanti su Anteprima 1312 <https://github.com/italia/ansc/issues/1067>
- Matrimonio stranieri: [3.1.3.1.1.1] Matrimonio con rito civile di stranieri non domiciliati né residenti <https://github.com/italia/ansc/issues/1072>
- Atti morte certificati: aggiunto stato civile del defunto
- [SC]: R008 - Consultazione notifiche: non vengono restituiti in response i datiPaginazione <https://github.com/italia/ansc/issues/1074>
- Gestione Mapped Diagnostic Context (MDC) al fine di aggiungere informazioni chiave di contesto
- [webapp]: Non permette di indicare il comune di nascita valido alla data <https://github.com/italia/ansc/issues/1078>
- [SC]: Firma USC per Rettifiche - Firma non avvenuta con successo. <https://github.com/italia/ansc/issues/1070> <https://github.com/italia/ansc/issues/1085>
- Proposta di aggiustamenti testo Annotazioni Automatiche. <https://github.com/italia/ansc/discussions/961>
- [SC]: usecase 411212 - dati obbligatori non reperibili perché inesistenti <https://github.com/italia/ansc/issues/1046>
- [SC]: Estratto per copia integrale - Errore interno <https://github.com/italia/ansc/issues/1029>
- Casi d'uso 433000 e 434000 (Web e SC) <https://github.com/italia/ansc/issues/1057>
- Aggiornamento annotazione contestuale unioni civili (regime patrimoniale)
- RettificaFacade: Errore di connessione nella creazione di un nuovo atto.null: java.lang.NullPointerException
- Annotazione automatica generata a seguito della trascrizione del decreto di cambio cognome/nome
- Atti matrimonio composizione: per soggetto diverso dal sindaco, vicesindaco o USC aggiunta nella composizione la dicitura "per delega avuta"
- Data formazione atto: aggiungere su tutti gli atti oltre alla data anche l'ora di formazione dell'atto

### Fixed Multilinguismo
- atti di nasccita in tedesco: Sesso bambino sempre in minuscolo
- matrimonio in tedesco: gibt der Erklärende (non der Erklärende gibt) den Namen XXX und den Zunamen XXX
- atti di morte in tedesco: Staatsbürgerschaft: italienische solo se ci sono i due punti, altrimenti mit italiensiche Staatsbürgerschaft come Nota 8 della nascita
- atti di morte in tedesco: Aggiungere lo stato civile del defunto anche se il deceduto è celibe/nubile und war ledig
- atti di morte in tedesco: usare la minuscola in "Folgendes erklärt"
- unioni civili in tedesco: Non "bewohner"(abitante) ma giusto "ansässig"(residente)
- trasversale in tedesco: Nelle date sostituire gli slash con i punti
- matrimonio in tedesco: die Vorgenannte è scritto maiuscolo: corretto se vi fosse scritto solo "la comparente". Poiché invece´nella formula la parola è seguita dalle generalità della stessa, vorgenannte va scritto minuscolo (es.: die vorgenannte Margherita Hack)
- aggiunta su tutti gli atti oltre alla data anche l'ora di formazione dell'atto
- unione civile: corretto: "in" amtlicher Kleidung (non"im" amtlicher Kleidung)
- unione civile: anziché "als Zeugen sind anwesend" andrebbe scritto "bei der Eheschließung waren als  Zeugen anwesend"
- matrimonio: atto di nascita con estremi numero .....Geburtsurkunde mit Einzelheiten non è corretto (non è possibile inserire solo "atto nr......xxx  Urk. Nr. xxx" ?
- richiesta trascrizione atto di morte all'estero richiesto da privati: Heute manca am
- trasversale: Se non é previsto un ulteriore qualifica per l'ufficiale che forma l'atto togliere , und (... vor mir, Michela Facchini, und Standesbeamten)

## [1.33.2 - 11-10-2024]

### Fixed

- [webapp]: errore 500 su estratto integrale <https://github.com/italia/ansc/issues/1081>
- [SC]: Annotazione per Rettifica (14630000) - Messaggio "errore interno" <https://github.com/italia/ansc/issues/1066>

## [1.33.1 - 10-10-2024]]

### Fixed

- [SC]: Servizio generazione certificati plurilingue internazionali (R019) irraggiungibile <https://github.com/italia/ansc/issues/1075>
- Modifica template di creazione issue per i nuovi servizi cooperativi <https://github.com/italia/ansc/issues/1075>

## [1.33.0 - 03-10-2024]

## Added

- [feature] Annotazioni automatiche in lingua (ID 111)
- [feature] Gestione soggetto irreperibile (ID 124)
- [feature] Annotazione modificativa su atti cartacei (ID 95)
- [feature] Disabilitazione casi d'uso di servizio lato servizi cooperativi (ID 120)
- [feature] Gestione certificati internazionali (Convenzione Monaco, Vienna) (ID 67)
- [feature] Gestione riconciliazione con SoggettoCollegato in Annotazione Modificativa Generica
- [feature] Insieme casi d’uso aggiuntivi multilingua (ID 20.a)

- [decodifiche] Aggiunto valore in tipo allegato decodifica ANSC_9 DEC_TIPO_ALLEGATO: 105 = Processo Verbale (Redatto in luogo particolare da autorità incaricata).
- [decodifiche] Aggiunta decodifica ANSC_114 DEC_TIPO_CERT_INT per campo idTipoCertificato (ID 67)
- [casi d'uso] Aggiunto nuovo caso d'uso 1.4.8.6.0.0.0.0 (Dic_Nasc_998_5) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [casi d'uso] Aggiunto nuovo caso d'uso 2.3.5.1 (Morte_998_4) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [casi d'uso] Aggiunto nuovo caso d'uso 3.6.9.1.0.0 (Matr_998_4) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [casi d'uso] Aggiunto nuovo caso d'uso 4.5.9.1.0.0 (UnCiv_998_4) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [casi d'uso] Aggiunto nuovo caso d'uso 5.3.8.1.0 (Citt_998_4) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE

- [model_evento.yaml]
  - Aggiunto il campo flagIrreperibile in modelSoggetto
  - Aggiunto il campo soggettoCollegato di tipo modelSoggetto in modelAnnotazioneModificativa
- [R019_certificato_internazionale.yaml]
  - Definiti nuovi servizi per la gestione certificati internazionali:
  - /certificato-internazionale/preview/{version}
  - /certificato-internazionale/create/{version}
  - /certificato-internazionale/annotazioni/{version} per sola consultazione
  - /certificato-internazionale/sigle-enunciazioni/{version} per sola consultazione
  - Aggiunto ModelCertificatoInternazionale

- [versione] Aggiunta versione 100016

## Fixed

- Casi d'uso 433000 e 434000 (Web e SC) <https://github.com/italia/ansc/issues/1057>
- Nota tecnica: aggiunta numero comunale <https://github.com/italia/ansc/issues/980>
- [webapp]: atto di matrimonio celebrato con la presenza dell’interprete <https://github.com/italia/ansc/issues/801>
- Trascr_007 Allegato con Id 999 da sostituire con nuovo allegato
- [anteprima e certificazione]: corretta anomalia che a volte portava a un errore in fase di generazione di anteprima e certificati
- [SC]: R009 - errore validazione caso 14950000 Annotazione per adozione internazionale di minore <https://github.com/italia/ansc/issues/993>
- Nota tecnica e controlli bloccanti per atti rettificati
- [SC]: UC 3.4.2.0.0.0 - manca spazio firma per avvocati #1054 <https://github.com/italia/ansc/issues/1054>
- [SC]: KO anteprima atto UseCase 52341 <https://github.com/italia/ansc/issues/1050>
- [SC]: Dati in ingresso non corretti - Anteprima Atto <https://github.com/italia/ansc/issues/1016>
- Aggiornamento atto con modifica caso d'uso  - Controllo bloccante <https://github.com/italia/ansc/issues/1008>
- [WEBAPP, SC] - allegati del provvedimento di rifiuto <https://github.com/italia/ansc/issues/1013>
- [SC]: R009 - caso d'uso 344000 Accordo di modifica delle condizioni di separazione o divorzio (Sep_Div_004) <https://github.com/italia/ansc/issues/1017>
- [SC, WEBAPP] - Soggetto Padre mancante nello usecase 11227000 <https://github.com/italia/ansc/issues/1018>
- Caso d'uso 312111  matrimonio: minuta non corretta
- [SC]: UC 2102 ATTO DI MORTE CON DATA E ORA PRESUNTA <https://github.com/italia/ansc/issues/1026>

## [1.32.17 - 02-10-2024]

### Changed

- [versioni] fine validita versione 100013 prolungata al 2024-12-01
- [versioni] fine validita versione 100012 prolungata al 2024-11-01

## [1.32.16 - 01-10-2024]

### Changed

- [webapp] I comuni che non hanno aderito ad ANSC non possono accedere alla web app di stato civile in produzione (tranne gli utenti abilitati a inserire la richiesta di adesione)
- [R001/R009] I comuni che non hanno aderito ad ANSC non possono usare il servizio in produzione.

## [1.32.15 - 23-09-2024]

### Added

- [webapp] [Single sign-on Anagrafe/Elettorale/Stato civile (per utenti abilitati)](https://dait.interno.gov.it/servizi-demografici/circolari/circolare-dait-n76-del-19-settembre-2024)

### Fixed

- [SC]: R010 - R002 Anteprima/Estratto atto di matrimonio - atto di nascita sposa riportato 2 volte <https://github.com/italia/ansc/issues/1051>
- [webapp]: Nota tecnica errore evento annullato o firmato <https://github.com/italia/ansc/issues/1053>>

## [1.32.14 - 17-09-2024]

## Changed

[decodifiche] Aggiornamento testi in tedesco per le decodifiche tipo allegato

## Fixed

- aggiornamento testi in tedesco per la generazione formule rlative agli usecase: Dic_Nasc_001, Morte_001, Matr_001, Rico_003, Trascr_UnCiv_001, Citt_001, Citt_043, Morte_006, Dic_Nasc_100, Matr_007, UnCiv_001
- [SC]: Dati richiesti per il Segreatario Comunale <https://github.com/italia/ansc/issues/1023>
- [SC]: R007 errore firma evento di annotazione di rettifica <https://github.com/italia/ansc/issues/1025>
- [SC,WA] Unknown property 'DATE_FORMAT' ModelTrascrizioneNascita
- [WA] Nota tecnica : problema con atti consecutivi relativi a stessi soggetti non riconciliati
- [WA] Controllo bloccante nota tecnica

## [1.32.13 - 11-09-2024]

## Fixed

- [Notifica ANPR] - Risolto errore in fase di generazione della discordanza anagrafica <https://github.com/italia/ansc/issues/1022>
- Web App Atto riconoscimento padre dopo la nascita <https://github.com/italia/ansc/issues/1021>
- [decodifiche] Aggiornamento della descrizione usecase 11 per risolvere un typo

## [1.32.12 - 09-09-2024]

## Fixed

- [WA] - Errore applicazione nota tecnica a varie tipologie di atti <https://github.com/italia/ansc/issues/1015>
- [SC]: Validazione caso 333000 - errore per campi obbligatori richiesti ma non conosciuti dall'USC <https://github.com/italia/anpr/issues/1012>
- [SC]: Estratto integrale matrimonio /unione civile <https://github.com/italia/ansc/issues/1014>
- [SC]: Estratto per copia integrale - errore "Non trovata l'associazione tra il soggetto intestatario e l'evento" <https://github.com/italia/ansc/issues/1011>

## [1.32.11 - 04-09-2024]

## Fixed

[WA] - [1.3.9.9] Caso d'uso di servizio (trascrizioni nascita): aggiunto intestatario

## [1.32.10 - 02-09-2024]

### Changed

- [decodifiche] Modifica codice e rango consolato Madrid (ANSC 97) <https://github.com/italia/anpr/issues/4648>
- [webapp]: Ordinamento indice annuale per numero nazionale evento

### Fixed

- [webapp]: Indice annuale con dati duplicati <https://github.com/italia/ansc/issues/1003> (vanno generati nuovamente per avere quelli corretti)
- [webapp]: Richiesta estensione nota tecnica per consentire la modifica del dato tipologia nel ModelAttoCollegato <https://github.com/italia/ansc/issues/1004>
- [webapp]: CERTIFICATI DA WEB APP: aggiunta la ricerca richiedente
- [webapp]: UC 3.1.2.1.1.1 - Matrimonio con rito civile con delega di altro comune o consolato nella casa comunale: corretta minuta  <https://github.com/italia/ansc/issues/1005>
- [webapp]: [SC] caso d'uso 5.2.1.5.4 - trascrizione decreto cittadinanza: corretta minuta e aggiounto allegato  <https://github.com/italia/ansc/issues/1001>
- Trascrizione atto ANSC: corretto Tipo file Allegato non consentito <https://github.com/italia/ansc/issues/1009>
- [webapp]: UC 3.1.3.1.1.1: minuta non corretta in presenza interprete <https://github.com/italia/ansc/issues/999>
- [webapp]: matrimonio in imminente pericolo di vita, corretto interprete <https://github.com/italia/ansc/issues/996>
- [webapp][SC]: corretto controllo età per acquisto cittadinanza di un minore art. 14 <https://github.com/italia/ansc/issues/998>
- [SC]: R009 - errore validazione caso 14950000 Annotazione per adozione internazionale di minore <https://github.com/italia/ansc/issues/993>

## [1.32.9 - 23-08-2024]

## Fixed

-[SC]: Anteprima Per Presa Visione - Errore "Dati in ingresso non corretti" <https://github.com/italia/ansc/issues/994>

## [1.32.8 - 22-08-2024]

## Fixed

- [SC]: Mapping incompleto e Metadati su estratto per copia integrale invertiti <https://github.com/italia/ansc/issues/972>
- [SC]: Anteprima - Cittadinanza (cdu 52122) - Sezione "Atto Collegato" <https://github.com/italia/ansc/issues/975>
- [WA]: Riconoscimento del nascituro: corretta minuta dell'atto

## [1.32.7 - 16-08-2024]

## Fixed

- [SC]: Notifiche atti in ANPR - generazione notifiche in caso di nazionalità incompleta <https://github.com/italia/ansc/issues/992>

## [1.32.6 - 14-08-2024]

## Fixed

- [R002/R010]: Errore generazione di anteprima / certificati per caso d'uso 1352 (in presenza di alcuni dati specifici)

## [1.32.5 - 13-08-2024]

## Fixed

- [R003]: A volte il servizio di elenco comunicazioni non restituiva il campo 'contenuto' della comunicazione

## [1.32.4 - 09-08-2024]

## Fixed

- [R005]: Servizio di ricerca soggetto: non restituisce nulla <https://github.com/italia/ansc/issues/989> <https://github.com/italia/ansc/issues/990>

## [1.32.3 - 08-08-2024]

## Fixed

- [WA]: Corretto errore in nota tecnica per i casi d'uso di riconoscimento ante nascita
- [R002]: Corretta regressione estratti integrali: aggiunta la sezione frima remota USC
- [WA]: Corretta navigazione tramite breadcrumb del menu di amministrazione

## [1.32.2 - 07-08-2024]

## Fixed

- [SC]: Controllo validità version
- R009: Annotazione di rettifica per errore materiale - USC dell'operazione di firma diverso da chi ha firmato l'attestazione <https://github.com/italia/ansc/issues/982>
- Corretta regressione estratti integrali di matrimonio: eliminata frase impropria 'Questo documento verrà digitalizzato'

## [1.32.1 - 05-08-2024]

## Fixed

- descrizione idVersion 100015 (da 1.31 a 1.32)

## [1.32.0 - 01-08-2024 (preproduzione, in produzione dal 07-08-2024]

## Added

- [feature] Gestione identificativo unico ANPR (ID 101)
- [feature] Collegamento anagrafiche diverse per uno stesso soggetto (ID 84.a)
- [feature] Gestione consolato nei matrimoni / unioni civili come organo delegante (modifica e adeguamento formula 120) (ID 113.a)
- [feature] Inserimento nuovi allegati per i casi d’uso matrimonio (ID 125) issue <https://github.com/italia/ansc/issues/932>

- [model_evento.yaml]
  - Aggiunto il campo in modelSoggetto: 
    - idANPR (id unico ANPR)
  - Aggiunti i seguenti campi in modelMatrimonio: 
    - idNazioneDelegante
    - nomeNazioneDelegante
    - idAnagraficaConsolatoDelegante 
    - nomeAnagraficaConsolatoDelegante 
  - Aggiunti i seguenti campi in modelUnioneCivile:
    - idNazioneDelegante
    - nomeNazioneDelegante
    - idAnagraficaConsolatoDelegante
    - nomeAnagraficaConsolatoDelegante

- [versione] Aggiunta versione 100015
- R005_servizi.yaml
   - Aggiornato CriteriRicercaSoggetto per supporto di idUnicoNazionale
   - Aggiornato il ModelSoggettoInt con campo: idANPR (id unico ANPR)
- R018_servizi.yaml
  - Definito nuovo servizio per la riconciliazione di due soggetti: /servizi/soggetto/riconciliazione/{version}

## Fixed

- [model_evento.yaml]
  - Modificati description ed example del campo luogoFiliazione in ModelDatiDiNascitaML adeguandolo al quello presente in ModelDatiDiNascita.
  - Aggiunto campo mancante in ModelMatrimonio: enteEstero

- [Servizi/Web App]  
  - R009 [SC] Atti di Nascita: Nuovi campi per AIRE e flusso Notifiche <https://github.com/italia/ansc/issues/979>
  - Adeguamento nota tecnica per correzione regime patrimoniale in unioni civili/matrimoni
  - R009 [SC] Model matrimonio incompleto <https://github.com/italia/ansc/issues/977>
  - Tag LuogoFiliazione <https://github.com/italia/ansc/issues/958>
  - R002 Certificato di nascita con paternità e maternità, corretto ordine del cognome e nome dei genitori e del soggetto
  - [webapp] Firma dichiarante UC 442000  <https://github.com/italia/ansc/issues/946>
  - R002 [SC/webapp] Anteprima Atto / Certificazione: modalità di visualizzazione di Località Estera e Stato di Nascita <https://github.com/italia/ansc/issues/966>
  - [SC]: Annotazione per adozione internazionale di minore - Dati mancanti necessari per l'annotazione di adozione (tipologia/attoNascita/attoAdozione) <https://github.com/italia/ansc/issues/920>
  - Dichiarazione nascita presentata da sanitario o procuratore speciale: resa opzionale la cittadinanza dei soggetti collegati
  - R009 Caso d'uso per cambio cognome/nome da Tribunale <https://github.com/italia/ansc/issues/913>
  - R009 matr_019 - Sesso testimone obbligatorio <https://github.com/italia/ansc/issues/957>
  - R008 - corretto esito della risposta del servizio idEsito=999 ma sembra tutto ok <https://github.com/italia/ansc/issues/951>
  - R009 Trascrizione matrimonio con rito religioso​: annotazione contestuale automatica <https://github.com/italia/ansc/issues/863>
  - R010 Anteprima - Matrimonio Fuori dalla Casa Comunale (cdu 311211): Numero Civico del Luogo Celebrazione <https://github.com/italia/ansc/issues/963>
  - R009: 11214100 Dichiarazione nei termini di filiazione fuori dal matrimonio resa all'USC dal procuratore del padre di bimbo nato morto <https://github.com/italia/ansc/issues/955>
  - R009: Casi d'uso Trascrizioni Matrimoni (use case 331000, 332000, 339999) e Riconciliazioni (use case 350000) <https://github.com/italia/ansc/issues/954>
  - R009: Caso d'uso Trascr_021/Trascr_020: dati sentenza tribunale italiano <https://github.com/italia/ansc/issues/942> <https://github.com/italia/ansc/issues/944>
  - [R002/webapp]: Anteprima Atto / Certificazione: Matrimonio estero VS Unione Civile Estero <https://github.com/italia/ansc/issues/967>
  - Anteprima Conformità: Controllo su Firma Dichiaranti - Messaggio di Errore <https://github.com/italia/ansc/issues/970>

### Changed

- Comunicazione: Disattivazione dei servizi cooperativi relativi ad alcuni casi d’uso di servizio <https://github.com/italia/ansc/discussions/882>

## [1.31.2 - 26-07-2024]

## Changed

- Aggiornata la guida per l'adesione ad ANSC

## Fixed

- [versione] [SC]: idVersion 100011 scaduto, nonostante dataFineValidita = 01/10/2024 <https://github.com/italia/ansc/issues/976>

## [1.31.1 - 25-07-2024]

## Fixed

- [documentazione] [SC]: Caso Uso 52154 - Mapping incompleto e Metadati su estratto per copia integrale non coerenti <https://github.com/italia/ansc/issues/972>

## [1.31.0 - 23-07-2024]

## Added

- [feature] Cruscotti di adesione al sistema ANSC (ID 43)
- [Guida adesione ANSC](Guida_adesione_ANSC.pdf)

## [1.30.1 - 01-07-2024]

## Fixed

- [5.2.1.5.4] Trascrizione del decreto per matrimonio-unione civile-naturalizzazione-da consolato  issue <https://github.com/italia/ansc/issues/949>

## [1.30.0 - 01-07-2024]

## Added

- [feature] Modifica per correzione di eventi di tipo annotazioni (ID 86)
- [feature] Gestione ulteriori usi specifici certificati (ID 76.a)
- [feature] Matrimoni tra stranieri con pubblicazioni da consolato, da comune e consolato ecc. (ID 113)
- [decodifiche] Aggiunta decodifica ANSC_113 - Tipo uso  DEC_TIPO_USO:
  - 1 = Art. 40 comma 2 DPR 445/2000
  - 2 = Certificati da produrre all'estero
  - 3 = Procedimenti giudiziari contenziosi
  - 4 = Norme sulla condizione dello straniero e immigrazi
  - 5 = Formalità ipotecarie e catastali
  - 6 = Servizio Elettorale
- model_evento.yaml
  - Aggiunti campi nel ModelEvento come segue, di tipo ModelSoggetto:
          madreBiologica
          padreBiologico
  - Aggiunti campi nel ModelPubblicazione come segue, di tipo String: 
          idNazione
          nomeNazione
          idAnagraficaConsolato
          nomeAnagraficaConsolato
    
- R008_notifiche.yaml
  - Aggiunti campi in NotificaAnpr come segue
             idTipoNotifica: # Identificativo univoco della notifica
          idComuneMittente: # Identificativo univoco del comune mittente della notifica
          idComuneDestinatario: # Identificativo univoco del comune destinatario della notifica
          dataIns: # Data di inoltro della notifica

- R002_certificazione.yaml
  - Aggiunto campo in CertificatoRequest come segue
    idTipoUso: # Identificativo univoco del tipo uso (codificato ANSC_113)
- R017_annotazione_rettifica.yaml
  - Aggiunto il nuovo servizio: /annotazione-rettifica/validazione/evento/{version} (validazione correzione di annotazione - ID 86)

## Fixed

- R005_consultazione_ansc.yaml
- Esplicitata response aggiuntiva: $ref: '#/components/schemas/ConsultazioneANSCSoggettoRevision1Response' contenente: $ref: '#/components/schemas/ModelSoggettoInt'
- R009: Casi d'uso Trascr_014, Trascr_020, Trascr_021: obbligatorietà genitori <https://github.com/italia/ansc/issues/940>
- R009: Unioni civili: sesso degli uniti civilmente da rendere obbligatorio
- R009: Validazione UC 51107 Citt_044 <https://github.com/italia/ansc/issues/930>
- R009: Matrimoni : "Riduzione dei termini di pubblicazione" in un solo comune
- R002: Estratti per copia integrale atti di morte <https://github.com/italia/ansc/issues/924>
- R009 Unioni Civili: 412111  e 411111 corretto Presente provvedimento che estingue il giudizio di opposizione
- R009 UC 1344 - Trascrizione della sentenza di adozione di maggiorenne emessa dal tribunale [Trascr_016] <https://github.com/italia/ansc/issues/794>
- R009 CASO D'USO 342000 (ACCORDO DI SCIOGLIMENTO O CESSAZIONE DEGLI EFFETTI CIVILI DEL MATRIMONIO): data conferma accordo da rendere opzionale <https://github.com/italia/ansc/issues/890>
- Annotazione automatica a seguito di divorzio (form 138-ter) <https://github.com/italia/ansc/issues/891>
- R009 Trascrizione matrimonio - metadati non presenti in Estratto e Anteprima <https://github.com/italia/ansc/issues/884>
- Template certificati ed estratti per riassunto: corretto numero nazionale
- Estratti per copia integrale: eliminata tipologia di atto
- R009 3.3.9.9.9.9 - Estratto integrale mancano tra i metadati i dati di celebrazione matrimonio <https://github.com/italia/ansc/issues/923>
- R009 ATTO CONFERMA SEPARAZIONE / DIVORZIO (Caso d'uso 343000) <https://github.com/italia/ansc/issues/892>
- [Wep App] - Servizio Anterprima - freemarker.core.InvalidReferenceException <https://github.com/italia/ansc/issues/928>
- R009 Validazione caso 14850000 - Annotazione modificativa generica <https://github.com/italia/ansc/issues/936>
- R002 Anteprima Atto KO - caso d'uso 12212300- Riconoscimento materno di nascituro <https://github.com/italia/ansc/issues/945>
- R009 Dichiarazione di nascita: luogo nascita obbligatorio <https://github.com/italia/ansc/issues/842>
- Annotazione automatica atto di nascita a seguito di trascrizione del decreto di acquisto della cittadinanza italiana: form.140
- R009 Atto di matrimonio - pubblicazioni in consolato <https://github.com/italia/ansc/issues/822>
- R008 ricerca-notifiche-anpr: Dati notifica ANPR collegata ad evento ANSC <https://github.com/italia/ansc/issues/470>
- Separazioni / divorzi: notifiche <https://github.com/italia/ansc/issues/677> <https://github.com/italia/ansc/issues/915> <https://github.com/italia/ansc/issues/916>
- R009 Validazione 1312 nuovi campi obbligatori <https://github.com/italia/ansc/issues/937>
- R005: Consultazione ANSC - aggiornare documentazione <https://github.com/italia/ansc/issues/895>
- R009: Errore validazione annotazione per adozione internazionale di minore <https://github.com/italia/ansc/issues/920>
- R009 Caso d'uso Trascr_020: flag richiedente madre/intestatario <https://github.com/italia/ansc/issues/948> <https://github.com/italia/ansc/issues/941>

## Removed

- [casi d'uso] Rimosso caso d'uso 2.2.1.4 (Morte_014) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE (ID 119)
- R002_certificazione.yaml
- Rimosso il seguente campo in CertificatoRequest in quanto equivale al idTipoUso=2 :
    validoEstero: # Indica opzione di validità per l'estero alla richiesta dei certificati semplici e per riassunto

## [1.29.5 - 17-06-2024]

### Fixed

- [SC/WA]: Template certificati/estratti e anteprime: corretta intestazione intestatario con secondo nome dopo la virgola
- [SC]: firma dichiarazione conformità - NullPointerException <https://github.com/italia/ansc/issues/912>
- [SC]: Fix controllo comune monolingua <https://github.com/italia/ansc/issues/927>
- Annotazione automatica a seguito di cittadinanza <https://github.com/italia/ansc/issues/896>
- [WA] 332000 : corretta nota tecnica in errore su firma USC
- [3.3.2.0.0.0] Trascrizione matrimoni dall'estero - richiesta di trascrizione da parte del consolato/ambasciata <https://github.com/italia/ansc/issues/914> <https://github.com/italia/ansc/issues/931>

## [1.29.4 - 12-06-2024]

### Fixed

- [SC]: Anteprima per presa visione - Dati in ingresso non corretti <https://github.com/italia/ansc/issues/919>
- [SC] Verifica servizio validazione per idVersion passati <https://github.com/italia/ansc/issues/918>

## [1.29.3 - 06-06-2024]

### Added

- [docs] [Quickstart multilingua servizi cooperativi](Note/SpecificheMultilingua/QuickstartMultilingua.md)

### Fixed

- [SC]: R001 Verifica Allegato <https://github.com/italia/ansc/issues/917>
- Certificati/estratti: Mancanza comune nascita se non valido alla data
- DISCREPANZA TRA ANTEPRIMA E CERTIFICAZIONE <https://github.com/italia/ansc/issues/898>
- REWORK [webapp]: Matrimonio STRANIERI (3.1.1.1.1.1 Matrimonio con rito civile nella casa comunale) <https://github.com/italia/ansc/issues/828>

## [1.29.2 - 04-06-2024]

### Fixed

- [SC]: Nuove casistiche vers.1.29 <https://github.com/italia/ansc/issues/905>
- [webapp]: [SC]: R012 firma dichiarante elettronica <https://github.com/italia/ansc/issues/902> <https://github.com/italia/ansc/issues/906> <https://github.com/italia/ansc/issues/907>
- [SC]: Annotazione automatica non approvata <https://github.com/italia/ansc/issues/903>

## [1.29.1 - 01-05-2024]

### Fixed

- [webapp]: impossibile generazione otp per uso servizi cooperativi <https://github.com/italia/ansc/issues/900>

## [1.29.0 - 31-05-2024]

NOTA: L'attività 85 Gestione soggetti AIRE ha comportanto l'aggiunta di campi opzionali a quasi tutti i caso d'uso

### Changed

- Estendere la durata di tutte le versioni a partire dalla 100011 fino al 31 settembre

### Added

- [feature] Gestione del provvedimento di rifiuto (ID 60)
- [feature] Gestione dei soggetti AIRE (ID 85)
- [feature] Gestione del multilinguismo (solo in ambiente di pre produzione) (ID 20)
- [feature] Trascrizione atto unione civile su richiesta dell'interessato per art. 19 (ID 103)
- [feature] Trascrizione atto morte su richiesta dell'interessato per art. 19 (ID 104)
- [feature] Trascrizione atto nascita su richiesta dell'interessato per art. 19 (ID 105)
- [feature] Matrimoni di stranieri con omissioni pubblicazioni (ID 112)
- [versione] Aggiunta versione 100013
- [decodifiche] Aggiunti valori in tipo allegato decodifica ANSC_9 DEC_TIPO_ALLEGATO: 102 = Provvedimento di rifiuto, 103 = Nullaosta di cui all'art. 116 o documentazione equivalente.
- [decodifiche] Aggiunta decodifica ANSC_111 Tipo Rifiuto DEC_TIPO_RIFIUTO (1 = Notifica, 2 = Atto).
- [casi d'uso] Aggiunto nuovo caso d'uso 1.3.1.5 (Trascr_027) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [casi d'uso] Aggiunto nuovo caso d'uso 2.2.1.4 (Morte_014) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [casi d'uso] Aggiunto nuovo caso d'uso 3.1.3.1.1.1 (Matr_019) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [casi d'uso] Aggiunto nuovo caso d'uso 4.3.6.0.0.0 (Trascr_UnCiv_005) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [feature] Inserimento provvedimento di rifiuto per notifica e/o atto (ID 60)
- [feature] Gestione residenza comune AIRE (ID85)
- [model evento] Nuovo campo dataProvvedimentoCambioCognome Aggiunto campo datiRifiuto relativi al provvedimento di rifiuto
  ```
    datiRifiuto:
    $ref: '#/components/schemas/ModelRifiuto'

    ModelRifiuto:
      properties:
        eventoCollegato:
          $ref: '#/components/schemas/ModelAttoCollegato'
        idNotifica:
          type: number
          description: id della notifica che si sta andando a rifiutare (tipo rifiuto 2)
        idTipoRifiuto:
          type: number
          description: tipo di rifiuto (1 - notifiche, 2 - evento)
        motivazioneRifiuto:
          type: string
          description: motivazione del rifiuto
        numeroProtocolloProvvedimento:
          type: string
          description: numero protocollo del provvedimento di rifiuto
  ```
- [model evento] Aggiunti i seguenti campi nel ModelSoggetto per la gestione della comuneAIRE (ID85)
  ```
    idComuneAIRE:
      type: string
      description: ID del Comune di Iscrizione AIRE
      example: '122'
    nomeComuneAIRE:
      type: string
      description: Nome del Comune di iscrizione AIRE
      example: 'Roma'
    idProvinciaAIRE:
      type: string
      description: ID della provincia di iscrizione AIRE
      example: '123'
    siglaProvinciaAIRE:
      type: string
      description: Sigla della provincia di Iscrizione AIRE
      example: 'RM'  
    flagTrasmissioneResidenzaEstera: 
      type: boolean
      description: indica che va gestita la residenza estera
      example: false
  ```

- R016_evento_rifiuto.yaml
  - Aggiunto nuovo servizio: /rifiuto/validazione/evento/{version} (validazione del provvedimento di rifiuto)
- R005_consultazione_ansc.yaml
  - Aggiunto nuovo servizio: /consultazione/ansc/evento/rifiuti/{version} (Consultazione dei provvedimenti di rifiuto presenti)

### Fixe
- [SC]: Validazione Annotazione - Errore Interno <https://github.com/italia/ansc/issues/861>
- [SC] Mapping casi d'uso relativi alle annotazioni - campi mancanti <https://github.com/italia/ansc/issues/741>
- Anteprima atto per presa visione <https://github.com/italia/ansc/issues/849>
- Consultazione atto: eliminare intervallo temporale accanto al comune di nascita <https://github.com/italia/ansc/issues/777>
- [webapp]: caso d'uso 2224 - Trascrizione di morte: Trascrizioni di sentenze di accertamento morte gia' dichiarata presunta <https://github.com/italia/ansc/issues/859>
- [Webapp - SC] Errata configurazione UC 1364 Scelta del cognome del figlio maggiorenne.<https://github.com/italia/ansc/issues/864>
- Trascrizioni atti dall'estero: firma dichiarante <https://github.com/italia/ansc/issues/676>
- Web app: Formazione atto matrimonio da web app (rito civile) <https://github.com/italia/ansc/issues/850>
- [webapp]: 312111 - Matrimonio su delega di altro comune  <https://github.com/italia/ansc/issues/841>
- ID112 - Matrimonio STRANIERI (3.1.1.1.1.1 Matrimonio con rito civile nella casa comunale) <https://github.com/italia/ansc/issues/828>
- [SC]: anomalia testo notifica di tipo annotazione matrimonio <https://github.com/italia/ansc/issues/845>
- Anteprima - Matrimonio: ordine dei firmatari in calce all'atto <https://github.com/italia/ansc/issues/809>
-  Anteprima : Dichiarazioni nascita ordine firmatari <https://github.com/italia/ansc/issues/812>
- Web app:  Mancato recupero di un atto in n stato firmato per conformità stato 11 con firma dichiarante digitale. <https://github.com/italia/ansc/issues/894>
- [webapp]: nota tecnica - visualizzazione allegati firmati (p7m) <https://github.com/italia/ansc/issues/689>
- Web app: tasto funzione 'ottieni atto' fuorviante <https://github.com/italia/ansc/issues/851>


## [1.28.9 - 29-05-2024]

### Changed

- [docs] Aggiornata la documentazione, erroneamente pubblicata nella versione 1.28.8 <https://github.com/italia/ansc/issues/897>

### Fixed

- [SC]: URGENTE versione 1.28.8! mapping matr_riconc_001 ritornato pre modifiche 1.28.4 <https://github.com/italia/ansc/issues/897>

## [1.28.8 - 29-05-2024]

### Changed

- [docs] Aggiornata model evento con la proprietà datiAdozioneMinoriInternazionale mancante in precedenza <https://github.com/italia/ansc/issues/893>
- [docs] Corrette alcune entri del changelog mapping (in particolare alcune etichette e campi non più controllati) <https://github.com/italia/ansc/issues/893>
- [docs] Integrata documentazione R015 : adozioni internazionali <https://github.com/italia/ansc/issues/893>

### Fixed

- [SC]: evento.datiAdozioneMinoriInternazionale mancante <https://github.com/italia/ansc/issues/893>
- [webapp]: Mancato recupero di un atto in n stato firmato per conformità stato 11 con firma dichiarante digitale. <https://github.com/italia/ansc/issues/894>

## [1.28.7 - 27-05-2024]

### Fixed

- [R002] Gestione data annotazione in estratto integrale <https://github.com/italia/ansc/issues/885>

## [1.28.6 - 16-05-2024]

### Changed

- [R012] Invio email : Gestione messaggio di errore dati firmatario incongruenti <https://github.com/italia/ansc/issues/867>

### Fixed

- Matrimonio con Rito Civile nella casa comunale 311111: annotazione errata #866 <https://github.com/italia/ansc/issues/866>

## [1.28.5 - 14-05-2024]

### Fixed

- [R005]: La ricerca per Intestatario, non restituisce il Comune di nascita <https://github.com/italia/ansc/issues/865>

## [1.28.4 - 08-05-2024]

### Added

- [documentazione]: [readme mapping](Mapping_casi_uso/readme_mapping.md), <https://github.com/italia/ansc/discussions/837>

## [1.28.3 - 06-05-2024]

### Fixed

- [webapp]: Impossibile emissione certificati per eventi di decesso <https://github.com/italia/ansc/issues/855>
- [documentazione]: Integrato changelog mapping

## [1.28.2 - 03-05-2024]

### Fixed

- [webapp]: Matrimonio su delega altro Comune: minuta non corretta <https://github.com/italia/ansc/issues/852>

## [1.28.1 - 03-05-2024]

### Fixed

- [SC]: Anteprima certificati - annotazioni troncate <https://github.com/italia/ansc/issues/853>

## [1.28.0 - 30-04-2024]

### Added

- [feature] Annotazione modificativa per adozioni internazionali (ID 102)
- [feature] Gestione certificazione per usi specifici (uso matrimonio) (ID 76)
- [feature] Riconciliazione matrimonio in un comune diverso da quello di registrazione dell’atto (ID 108)
- [feature] Registri annuali per comune (ID 94)
- [versione] versione 100012
- [decodifiche] Aggiunta decodifica ANSC_108 - Tipo dati adozione
- [R002] Aggiunto il servizio per la validazione delle annotazione modificativa per adozioni internazionali
- [casi d'uso] Aggiunto nuovo caso d'uso 1.4.9.5.0.0.0.0 (Dic_Nasc_998_4) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE
- [notifiche anagrafe] Aggiunte nelle notifiche da ANSC verso ANPR le informazioni relative alla cittadinanza e alla residenza sia dell’intestatario dell’atto (non per l’atto di nascita) che dei genitori in caso di atti di nascita (ID 126)

### Changed

- c Nuovo modello ModelAdozioneMinoriInternazionale per ID 102
- [model evento] Nuovi campi  luogoEventoMatrimonio, attoAccordoSeparazione, attoConfermaAccordoSeparazione, attoNegoziazioneAssistita, officianteEventoMatrimonio, dataEventoMatrimonio in ModelRiconciliazione
- [model evento] Nuovo campo dataProvvedimentoCambioCognome
- [R002] Nuovo campo usoMatrimonio in CertificatoRequest del servizio /certificato/{version}
- [R005] Rilassati controlli della request su R005 /consultazione/ansc/soggetto/{version} per permettere la ricerca degli eventi per nome, cognome e data di nascita dell'intestatario #802
- [R001] Resa consultabile l'anteprima pdf di un'annotazione automatica non ancora approvata <https://github.com/italia/ansc/issues/840>

### Deprecated

- [model evento] Reso deprecato il campo dataProvvidementoCambioCognome

### Fixed

- [R009] Casi d'uso 12221122/RICO_004 e 12222121/RICO_007: controlli su obbligatorietà dati di riconoscimento della madre/padre <https://github.com/italia/ansc/issues/682>
- (ID108) Riconciliazione matrimonio in un comune diverso da quello di registrazione dell’atto <https://github.com/italia/ansc/issues/717> <https://github.com/italia/ansc/issues/708>
- Trascr_012 - Trascrizione del decreto prefettizio di cambiamento del nome e cognome <https://github.com/italia/ansc/issues/721>
- Annotazioni: [3.6.6.9.9.9] Caso d'uso di servizio (comunicazione da altri comuni)
- COMUNICAZIONI/ANNOTAZIONI AUTOMATICHE PER CASO D'USO 350000 RICONCILIAZIONE <https://github.com/italia/ansc/issues/766>
- Web App - indicazione ultimo numero comunale
- Web app - Caso d'uso Morte_004 <https://github.com/italia/ansc/issues/791>
- Trascrizione ex articolo 19: annotazioni automatiche impropriamente generate <https://github.com/italia/ansc/issues/796>
- Dichiarazione di matrimonio (religiosi e civili): data annotazione contestuale errata <https://github.com/italia/ansc/issues/797>
- [SC] Validazione controllo valore certificabile <https://github.com/italia/ansc/issues/800>
- [SC] update intestatario per evento confermato <https://github.com/italia/ansc/issues/803>
- Certificazione: data annotazione contestuale matrimonio <https://github.com/italia/ansc/issues/807>
- Estratti integrali - Trascrizioni estere: non visualizzare il metadato 'riassunto trascrizione' negli estratti integrali <https://github.com/italia/ansc/issues/808>
- R002 certificazioni matrimoni esteri e nelle annotazioni (form. 132) <https://github.com/italia/ansc/issues/813>
- Web App [5.2.1.2.3] Straniero riconosciuto durante la maggiore età da cittadino italiano <https://github.com/italia/ansc/issues/816>
- [SC] Errore mapping property dataProvvidementoCambioCognome <https://github.com/italia/ansc/issues/818>
- [SC] Validazione atti - insert id intestatario
- Estratti di matrimonio, comune di nascita <https://github.com/italia/ansc/issues/820>
- Web App - formula 16 <https://github.com/italia/ansc/issues/819>
- Web app: Registrazione unione civile <https://github.com/italia/ansc/issues/823>
- caso d'uso Trascr_018 <https://github.com/italia/ansc/issues/727>

## [1.27.7 - 22-04-2024]

### Fixed

[webapp] comportamento di verifica ausilioInterprete in caso venga inviato un valore non censito; per default il valore non censito viene considerato come false.

## [1.27.6 - 18-04-2024]

### Added

- aggiunto comportamento revision <https://github.com/italia/ansc/blob/main/docs/Revision.md>

### Changed

- [webapp] adeguato comportamento di verifica ausilioInterprete in caso venga inviato un valore non censito; per default il valore non censito viene considerato come false.
- [R005] aggiunta revision [2000002](https://github.com/italia/ansc/blob/main/docs/Revision.md), adegua l'output del path /consultazione/ansc/intestatario a quanto dichiarato nell'openapi <https://github.com/italia/ansc/issues/827>
- [R008] aggiunta revision [2000003](https://github.com/italia/ansc/blob/main/docs/Revision.md), adegua l'output del path /notifiche/getNotificheByEvento a quanto dichiarato nell'openapi <https://github.com/italia/ansc/issues/830>

## [1.27.5 - 15-04-2024]

### Changed

- aggiornamento nota tecnica: reso possibile modificare la descizione del caso d'uso
- aggiornamento nota tecnica: reso obbligatorio l'inserimento del motivo di utilizzo

## [1.27.4 - 12-04-2024]

### Changed

- [documentazione]: Specificato perimetro di utilizzo della nota tecnica (nella sezione relativa di Guida operativa ANSC).

## [1.27.3 - 11-04-2024]

### Fixed

- [certificazione]: declinato il femminile e maschile dello stato civile dell'intestario negli atti di morte <https://github.com/italia/ansc/issues/815>
- [webapp]: reso possibile predisporre la bozza di un unione civile in anticipo (calendario data evento reso libero) <https://github.com/italia/ansc/issues/811>

## [1.27.2 - 04-04-2024]

### Fixed

- [validazione evento]: Controllo dichiarazione tardiva di nascita oltre i 10 giorni <https://github.com/italia/ansc/issues/804>

## [1.27.1 - 29-03-2024]

### Fixed

- [webapp]: malfunzionamento gestione allegati <https://github.com/italia/ansc/issues/798>
- [R009]: errore gestito invece quando viene inviato un tipo dato non coerente <https://github.com/italia/ansc/issues/794>


## [1.27.0 - 27-03-2024]

### Added

- [feature] Gestione allegati e attestazione conformità in nota tecnica (ID 100.a)
- [feature] Gestione decreto prefettizio con modifica nome e/o cognome (ID 84)
- [feature] Trascrizione atto matrimonio su richiesta dell'interessato per art. 19 (ID 99)
- [versione] versione 100011
- [decodifiche] nuovo tipo allegato alla decodifica ANSC_08 DEC_TIPO_ALLEGATO: id:101 Descrizione: "Processo verbale di dichiarazione di morte".
- [casi d'uso] Aggiunto nuovo caso d'uso 3.3.6.0.0.0 (Trascr_Matr_006) ed aggiornata la decodifica ANSC_03 DEC_USE_CASE

### Changed
 
- [model evento] Nuovo campo attoNascitaDeceduto in ModelDatiEventoMorte
- [model evento] Nuovo campo attoNascitaDeceduto in ModelTrascrizioneMorte
- [model evento] Nuovo campo flagCambioGeneralita in ModelTrascrizioneCittadinanza
- [model evento] Nuovo campo intestatarioVecchieGeneralita in ModelTrascrizioneCittadinanza

### Fixed

- [SC]: Controlli obbligatorietà caso d'uso 12999999 - Rico_999 <https://github.com/italia/ansc/issues/730>
- [Morte_005 usecase 2211 morte in viaggio per mare o aereo] Aggiungere allegato obbligatorio <https://github.com/italia/ansc/issues/655>
- Dichiarazioni tardive di nascita: controllo dei 10 gionri <https://github.com/italia/ansc/issues/774>
- Annotazione automatica a seguito di UC 1331: carattere di tabulazione in testo annotazione automatica <https://github.com/italia/ansc/issues/751>
- [SC]: Cancellazione Atto Servizio R011 <https://github.com/italia/ansc/issues/756>
- Web App: Annotazione contestuale in dichiarazioni di morte <https://github.com/italia/ansc/issues/775>
- Errore annotazione per errore materiale <https://github.com/italia/ansc/issues/761>
- Gestione del comune di registrazione dell’atto di nascita, negli atti di vita successivi <https://github.com/italia/ansc/issues/705>
- 51103: Straniero nato in italia che vi abbia risieduto legalmente senza interruzioni fino alla maggiore età <https://github.com/italia/ansc/issues/762>
- Usecase 51107 giuramento di cittadinanza con impedimenti: Minuta apparentemente scorretta <https://github.com/italia/ansc/issues/754>
- Ricerca eventi per intervallo temporale <https://github.com/italia/ansc/issues/692>
- Web App: Matrimonio rito civile su delega altro comune - minuta non corretta <https://github.com/italia/ansc/issues/765>
- [R009] - Variazioni delle generalità del cittadino, per i casi d'uso Citt_043, Citt_044 e Citt_045 <https://github.com/italia/ansc/issues/443>
- [SC]: data annotazione su notifica <https://github.com/italia/ansc/issues/773>
- [SC]: hasAllegatiDaAttestare=true anche quando l'atto non ha allegati <https://github.com/italia/ansc/issues/784>


## [1.26.6 - 25-03-2024]

### Fixed

- R001: errore download allegato Attestazione di conformità
  <https://github.com/italia/ansc/issues/786>


## [1.26.5 - 22-03-2024]

### Fixed

- R007: Errore nella firma remota dell'Attestazione di conformità
  <https://github.com/italia/ansc/issues/785>
- WebApp: Quando non tutti i dati dell'officiante erano impostati
  la firma dichiarante elettronica poteva andare in errore.


## [1.26.4 - 19-03-2024]

### Fixed

- R007: Veniva permessa la firma da parte dell'Ufficiale di Stato Civile
  anche senza la firma dei firmatari  <https://github.com/italia/ansc/issues/771>

  
## [1.26.3 - 18-03-2024]

### Fixed

- R007_firma_usc.yaml: Schema FirmaAttestazioneRequest parametriFirma modificato in firmaInput <https://github.com/italia/ansc/issues/772>


## [1.26.2 - 15-03-2024]

### Changed

- Modificato schema openapi AllegatoOutput in AnteprimaAttestazioneOutput <https://github.com/italia/ansc/issues/769>


## [1.26.1 - 12-03-2024]

### Fixed

- Generazione OTP per integrazione gestionale comunale


## [1.26.0 - 11-03-2024]

### Added
- Nuove funzionalità
  - Gestione attestazione conformità allegati a regime (ID 100)

- Processo
  - Web Application: Gestione della firma USC dell'Attestazione di conformità di eventuali allegati presenti nell'atto
  - Servizi cooperativi: Gestione della firma USC dell'Attestazione di conformità di eventuali allegati presenti nell'atto

- model_evento.yaml
  - Aggiunti campi dataEventoUnioneCivile,luogoEventoUnioneCivile,officianteEventoUnioneCivile in ModelScioglimentoUnioneCivile
  - Aggiunto campo confermaAccordoSeparazione in ModelSeparazione
  - Aggiunto campo flagAttestazione in ModelAllegatoRif
- R007_firma_usc.yaml
  - Aggiunto nuovo servizio: /attestazione/firma/{version} (per la firma USC dell'Attestazione di conformità)
- R010_anteprima.yaml
  - Aggiunto nuovo servizio: /attestazione/anteprima/{version} (per l'anteprima dell'Attestazione di conformità)
- Versione
  - Aggiunta versione 100010 (se l'evento viene acquisito con questa versione o successive, è obbligatorio firmare l'attestazione di conformità prima della firma dell'ufficiale di stato civile)
- Allegato
  - Aggiunto allegato con ID 100 "Atto di dichiarazione di nascita redatto dalla direzione sanitaria" obbligatorio in Trascr_022
  
### Fixed

- Web Application
  - [webapp]: dataAtto / dataFormazione / dataEvento - caso Unione Civile 
  <https://github.com/italia/ansc/issues/697>
  - NOTA tecnica: errore validazione evento con idVersion pregressi
  <https://github.com/italia/ansc/issues/759>
  - [3.4.2.0.0.0] Accordo di scioglimento (o di cessazione degli effetti civili) del matrimonio (divorzio): minuta non corretta 
  <https://github.com/italia/ansc/issues/709>

- Servizi cooperativi
  - R009: matrimonio con rito civile e Matr_999_1: nazionalità testimoni si richiede facoltativa
  <https://github.com/italia/ansc/issues/750>
  - R009: Inserito controllo coerenza tipoevento e tipocontenuto, e idUsecase 
  - [R002]: data non valorizzata nella copia integrale 
  <https://github.com/italia/ansc/issues/725> 
  - R009: 319999 - rendere opzionali i testimoni 
  <https://github.com/italia/ansc/issues/739>	
  - R009: 5.2.1.2.2 - Straniero nato in italia che vi abbia risieduto legalmente senza interruzioni fino alla maggiore età 
  <https://github.com/italia/ansc/issues/752> 
  - Trascrizione resa da direttore sanitario: reso obbligatorio allegato 'atto di dichiarazione di nascita'
  <https://github.com/italia/ansc/issues/748> 
  - R010: certificazione - Rico_006 errore in template certificazione/anteprima
  <https://github.com/italia/ansc/issues/745> 
  - R009: 3.4.8.0.0.0 - Mancata conferma divorzio in assenza di entrambi i coniugi
  <https://github.com/italia/ansc/issues/755> 
  - R009: Caso d'uso Dic_Nasc_999 - richiesta di aggiunta di un soggetto dichiarante facoltativo
  <https://github.com/italia/ansc/issues/734> 

-Trasversale
  - Annotazione automatica non corretta per atto di nascita a seguito di trascrizione di trascrizione atto di morte all'estero richiesto da pubblica autorità
  <https://github.com/italia/ansc/issues/740>
  - Annotazione automatica per atto di nascita generata a partire da trascrizione di atto di matrimonio
	<https://github.com/italia/ansc/issues/736>
  

## [1.25.3 - 08-03-2024]

### Fixed

- Data fine validità record 0 e 1 tabella 79 <https://github.com/italia/ansc/discussions/738>


## [1.25.2 - 05-03-2024]

### Fixed

- R005 - Integrazione documentazione consultazione soggetto intestatario <https://github.com/italia/ansc/issues/744>


## [1.25.1 - 05-03-2024]

### Fixed

- R005 - Consultazione Intestatario soggetto estero richiede comune o provincia di nascita <https://github.com/italia/ansc/issues/744>


## [1.25.0 - 29-02-2024]

### Added
- Nuove funzionalità
  - Nota tecnica senza la gestione degli allegati (ID 88)
    
- Processo
  - Web Application: Gestione delle Note Tecniche per atti completati contenenti metadati errati a causa di bug di sistema; la nota tecnica è utilizzabile solo da web application; lato servizi cooperativi è stato implementato il solo servizio di consultazione

- model_evento.yaml: i seguenti campi sono utilizzati nel servizio di consultazione nota tecnica
  - Aggiunti campi nel ModelEvento come segue:
  
```
            noteTecniche:
	          type: array
	          items:
	            type: string
	            description: lista delle note tecniche associate all'evento
            datiNotaTecnica:
              $ref: '#/components/schemas/ModelNotaTecnica'
            ModelNotaTecnica:
		      properties:        
		        eventoDaModificare:
		         $ref: '#/components/schemas/ModelAttoCollegato'
		        notaTecnica:
		          type: string         
		          description: nota tecnica associate all'evento
```

- Aggiunto valore 2 = NOTATECNICA alla decodifica ANSC_79
- Servizi cooperativi
  - R005_consultazione_ansc.yaml			
    - Aggiunto servizio: /consultazione/ansc/evento/note/tecniche/{version} (Ricerca di tutte le note tecniche afferenti all'evento passanto in input)

### Fixed

- Servizi cooperativi
  - Rimossi i campi nomeNazioneEnte e nazioneEnte dal ModelEnteEstero in quanto ereditati da modelEnteDichiarante dal file model_evento.yaml (https://github.com/italia/ansc/issues/719)
  - Annotazione modificativa generica: aggiunto controllo sull'id dell'intestario mancante (https://github.com/italia/ansc/issues/712)
  - Caso d'uso Rico_005: anomala richiesta campo "Riconoscimento genitore" (https://github.com/italia/ansc/issues/713)
  - [R009] per Matr_999_2: corretto controllo sul numeroTestimoni (https://github.com/italia/ansc/issues/715)
  - [R009] - Validazione Sep_Div_006 controllo errato su siglaProvinciaEnte dell'Autorità mittente (https://github.com/italia/ansc/issues/728)

- Web Application
  - Sciogl_UnCiv_005: errata configurazione della formula usata (https://github.com/italia/ansc/issues/722)

## [1.24.1 - 27-02-2024]

### Fixed

- corretta trascrizione resa da direzione sanitaria


## [1.24.0 - 22-02-2024]

### Added
    Versione
       - Aggiunta nuova versione 100009

    model_evento.yaml
        - Aggiunto campo nel ModelSoggetto come segue: 
         	    localitaEsteraNascita: 
                  type: string
                  description: Località estera di nascita
                  example: 'Madrid'       
                  
        - Aggiunti campi nel ModelEnteDichiarante come segue:       
                nazioneEnte:
                  type: string
                  description: Nazione dell'ente (decodifica ANPR_02)
                  example: "91"
                nomeNazioneEnte:
                  type: string
                  description: Descrizione della nazione
                  example: "AUSTRIA"
        - Aggiunto campo nel ModelDatiDiMorte come segue:
                comuneEstero: 
                  type: string
                  description: Comune Estero
                  example: 'Londra'         
### Fixed
	Servizi cooperativi
	   - Gestione comune estero https://github.com/italia/ansc/issues/674
	   - 346000 Trascrizione delle sentenze di deliberazione, da parte della Corte d’Appello, delle sentenze di nullità del matrimonio pronunciate dai Tribunali Ecclesiastici (Sep_Div_006) https://github.com/italia/ansc/issues/670
	   - USECASE 347000 Trascrizione provvedimenti esteri in materia matrimoniale. Sep_Div_007 https://github.com/italia/ansc/issues/673
	   - [R009] Errore Validazione Annotazione per Cambio Generalità Genitore https://github.com/italia/ansc/issues/680
	   - usecase 433000 Trascrizione di Unione Civile di sentenze di Tribunali stranieri - Richiesta di trascrizione da parte dell'interessato (Trascr_UnCiv_003) https://github.com/italia/ansc/issues/687
	   - Dichiarazione di morte: cittadinanza del comparente https://github.com/italia/ansc/issues/690
	   - [ws R009] Trascrizione Nascita (cdu 1399) - Dati genitori obbligatori https://github.com/italia/ansc/issues/691
	   - [SC]: 1399 trascrizione - metadati obbligatori per madre e padre https://github.com/italia/ansc/issues/695
	   - [SC]: R013 - Validazione Annotazione Modificativa - Errore senza alcuna descrizione https://github.com/italia/ansc/issues/699
	   - [webapp] - [SC]: Allegati per caso d'uso 332000 https://github.com/italia/ansc/issues/704
       - usecase trascr_matr_005 errore campo obbligatorio https://github.com/italia/ansc/issues/702


## [1.23.6 - 13-02-2024]

### Fixed   
	
	Servizi cooperativi
	   - R002/R010 Data annotazioni https://github.com/italia/ansc/issues/656
	   - caso d'uso 366999- Caso d'uso di servizio (comunicazione da altri comuni) https://github.com/italia/ansc/issues/661
	   - R002/R010 Accordo di separazione e Accordo di divorzio https://github.com/italia/ansc/issues/657
	   - R009 Trascrizione atto di separazione proveniente dall'estero https://github.com/italia/ansc/issues/663
	   - R009 Trascrizione atto separazione da Stato estero su richiesta dell'interessato https://github.com/italia/ansc/issues/639
	   - Negoziazione assistita: corrette annotazioni automatiche https://github.com/italia/ansc/issues/675
	   - R009/R002/R010 Trascrizioni atti dall’estero caso d’uso 332000 (matrimonio), 1311 (nascita), 2213 (morte): aggiornamento allegati ed etichette dei metadati nell'estratto integrale  https://github.com/italia/ansc/issues/658
	   - R010: Anteprima Atti (Unione Civile / Matrimonio), Sezione "Dati Evento": gestione della data https://github.com/italia/ansc/issues/672
	   - R002: corretto errore certificazione se richiedente con Id ANPR https://github.com/italia/ansc/issues/684


## [1.23.5 - 08-02-2024]

### Fixed   
	
	Servizi cooperativi
		- [R005] - obbligatorietà criteri ricerca intestatario https://github.com/italia/ansc/issues/671


## [1.23.4 - 07-02-2024]

### Fixed   
	
	Servizi cooperativi
		- [R005] - ricerca intestatario https://github.com/italia/ansc/issues/669


## [1.23.3 - 05-02-2024]

### Fixed   
	
	Servizi cooperativi
		- Servizi Cooperativi - Messaggi di errori non coerenti e da migliorare https://github.com/italia/ansc/issues/172
		- Il campo evento.datiDiMorte.siglaProvinciaMorte nella sezione Dati Riconoscimento - Dati di morte non corrisponde al pattern ^[0-9]*$ https://github.com/italia/ansc/issues/623
		- RICO_010 allegato obbligatorio https://github.com/italia/ansc/issues/634
		- Annotazione relativa ad atto di dichiarazione di acquisto di cittadinanza https://github.com/italia/ansc/issues/635
		- dic_nasc_033 allegati https://github.com/italia/ansc/issues/636
		- Annotazione per trascrizioni matrimonio e divorzio https://github.com/italia/ansc/issues/637
		- Divorzi/Separazione - Presenza Avvocati e Firma https://github.com/italia/ansc/issues/638
		- Consultazione evento dopo annotazioni correttive multiple https://github.com/italia/ansc/issues/640
		- [R005] - ricerca intestatario https://github.com/italia/ansc/issues/641
		- Dic_Nasc_059 -  mapping: sono obbligatori i dati dei genitori https://github.com/italia/ansc/issues/644
		- Anomalie cessazione effetti civili matrimonio (Sep_Div_005) https://github.com/italia/ansc/issues/647

	Web App
		- Trascrizione atti dall'estero https://github.com/italia/ansc/issues/593


## [1.23.2 - 29-01-2024]

### Fixed   	

	Servizi cooperativi
		- Testo Notifiche non corretto https://github.com/italia/ansc/issues/567 
		- ERRORE AMBIENTE TEST "Il campo evento.datiDiMorte.siglaProvinciaMorte nella sezione Dati Riconoscimento - Dati di morte non corrisponde al pattern ^[0-9]*$" https://github.com/italia/ansc/issues/623
		- ATTRIBUZIONE DI DUE O PIU’ NOMI (MASSIMO 3) SEPARATI DA VIRGOLA AI NEONATI https://github.com/italia/ansc/issues/588
		- TRASCR_018 e TRASCR_019 versione 1.23.0 https://github.com/italia/ansc/issues/630
		- Certificati: la frase art.15 deve essere alternativa alla frase valido per estero https://github.com/italia/ansc/issues/633
		- R006: corretto errore firma USC https://github.com/italia/ansc/issues/615
		- Trascr_018 e Trascr_019: adeguato comportamento dei servizi a quello della web app https://github.com/italia/ansc/issues/630
		
	Web App
		- Corretta minuta atto di matrimonio con Interprete: CASO D'USO 311111 https://github.com/italia/ansc/issues/618
		- Corretta minuta atto di Matrimonio legge patrimoniale https://github.com/italia/ansc/issues/619
		
	Trasversale
		- Gestione nomi con la virgola https://github.com/italia/ansc/issues/588
		- Corretto riferimento atto nelle certificazioni https://github.com/italia/ansc/issues/617
		- Migliorata stampa estratti https://github.com/italia/ansc/issues/598
		- Trascrizione del decreto di concessione della cittadinanza italiana: corretto modulo per firma analogica https://github.com/italia/ansc/issues/628
		- Divorzi / Separazione: corretta gestione presenza avvocati e firma https://github.com/italia/ansc/issues/638
		

## [1.23.1 - 22-01-2024]

### Fixed

    model_evento.yaml
        - Corretto annidamento del campo tipoNascitaSoggetto, che erronamenente non faceva parte di ModelDatiDiNascita: (https://github.com/italia/ansc/issues/629)
             tipoNascitaSoggetto: 
                type: string
                description: Identificativo del tipo di nascita del nascituro di cui si sta dichiarando la nascita (decodifica ANSC_107).
                example: '1'  


## [1.23.0 - 19-01-2024]

### Added
- Nuove funzionalità
  - Gestione atti inefficaci (ID 89)
    
- Versione
  - Aggiunta nuova versione 100008

- model_evento.yaml
  - Aggiunti campi nel ModelEvento come segue:
            operatoreFirmatario:
              type: string
              description: Codice fiscale dell'operatore che ha firmato l'atto.
              example: 'ABCDEF99A11H501A'
            operatoreFirmatarioNome:
              type: string
              description: Nome dell'operatore che ha firmato l'atto.
              example: 'MARIO'
            operatoreFirmatarioCognome:
              type: string
              description: Cognome dell'operatore che ha firmato l'atto.
              example: 'ROSSI'
  - Aggiunto campo nel ModelDatiDiNascita come segue:
             tipoNascitaSoggetto: 
                type: string
                description: Identificativo del tipo di nascita del nascituro di cui si sta dichiarando la nascita (decodifica ANSC_107).
                example: '1'  
    
    
- Decodifiche
  - Aggiunta decodifica ANSC_107 relativa allo stato di nascita del nascituro
    	
### Fixed   	

	Servizi cooperativi
	   - R001: corretto errore nella consultazione degli allegati di un atto redatto da altro comune (https://github.com/italia/ansc/issues/549)
	   - R009: Prenotazione Evento per parti gemellari (https://github.com/italia/ansc/issues/571) (https://github.com/italia/ansc/issues/611)
	   - R009: corretto errore Validazione atto Caso d'uso 1311 (https://github.com/italia/ansc/issues/580)
	   - R013: corretta rettifica evento di tipo Annotazione (https://github.com/italia/ansc/issues/519)
	   - R010: corrette annotazioni (https://github.com/italia/ansc/issues/507)
	   - R011: Cancellazione Atto - Eliminazione fisica / annullamento (https://github.com/italia/ansc/issues/489)
	   
	Trasversale
		- UC 329999: atto di matrimonio religioso da altro comune; campi testimoni resi non obbligatori (https://github.com/italia/ansc/issues/569)
		- Corretti certificati (art.15) (https://github.com/italia/ansc/issues/570)
		- Certificati: migliorati i template per differenziare cognome e nome (https://github.com/italia/ansc/issues/589)
		- CERTIFICAZIONE ATTO DI MORTE CASO D’USO 2101: differenziato lo stato civile de defunto in base al sesso celibe/nubile (https://github.com/italia/ansc/issues/597)
		- Corretta certificazione impossibile per atto di nascita (https://github.com/italia/ansc/issues/602)
		- Cittadinanza 52122 - richiesta firma dichiarante impropriamente (https://github.com/italia/ansc/issues/576)
		- Corretta gestione comuni stranieri nelle certificazioni (https://github.com/italia/ansc/issues/592)
		- Aggiunta dicitura su anteprima atto per firma digitale del dichiarante (https://github.com/italia/ansc/issues/578)
		- Corretta gestione Identificativo atto rispetto ad anno atto (https://github.com/italia/ansc/issues/599)
		- sep_div_004: corretta obbligatorietà allegati (https://github.com/italia/ansc/issues/612)
		- Trascrizione atto di morte caso d'uso di servizio: aggiunto comparenti non obbligatorio (https://github.com/italia/ansc/issues/601)
		- trascrizione di una nascita avvenuta all'estero: reso opzionale il campo estremi documento (https://github.com/italia/ansc/issues/600)
		- Trascrizione atti dall'estero: gestita obbligatorietò allegati in base a richiesta verbale o scritta (https://github.com/italia/ansc/issues/594)
		- Usecase 1351 Trascrizione provvedimento straniero di adozione (Trascr_018): corretta obbligatorietà metadati (https://github.com/italia/ansc/issues/520) (https://github.com/italia/ansc/issues/521)
		
	   
	Web Application
		- Corretto errore in annotazione per rettifica di un matrimonio (https://github.com/italia/ansc/issues/621)
		- Corretta gestione Form.81 - Verbale di giuramento (https://github.com/italia/ansc/issues/574)
		- Corretta gestione presenza interprete (https://github.com/italia/ansc/issues/591)
		- Corrette ricerche atti (https://github.com/italia/ansc/issues/596)
		- Usecase 51107 prestazione di giuramento (con impedimento): eliminata casistica di presenza interessato (https://github.com/italia/ansc/issues/550)


## [1.22.4 - 17-01-2024]

### Fixed

	Servizi cooperativi
		- R002: Verifica intestatario certificato per casi d'uso che non lo prevedono (https://github.com/italia/ansc/issues/620)
		

## [1.22.3 - 12-01-2024]

### Fixed

	Servizi cooperativi
		- R009 Validazione : controllo stato residenza estero (https://github.com/italia/ansc/issues/606)(https://github.com/italia/ansc/issues/605)

  
## [1.22.2 - 11-01-2024]

### Fixed

	Servizi cooperativi
		- R010 Anteprima: visualizzazione annotazioni contestuali multiple (https://github.com/italia/ansc/issues/607)


## [1.22.1 - 22-12-2023]

### Added

    Web application
       - Per i casi di servizio, dei registri Matrimonio, Unioni civili e Cittadinanza, se nell'accordion dell’intestatario viene utilizzata la ricerca tramite id ansc per inserire i dati di un soggetto, la ckeckbox “Firmatario” risulta erroneamente disabilitata non permettendo quindi di indicare il soggetto come firmatario dell’atto.


## [1.22.0 - 21-12-2023]

### Added

    Versione
       - Aggiunta nuova versione 100007

    Aggiunta decodifica ANSC_106 relativa alla separazione e il divorzio
   
    model_evento.yaml
       - Aggiunti campi nel ModelSeparazione come segue:
		   tipoSeparazioneDivorzio:
			type: string
			description: Discriminante tra separazione o divorzio (decodifica ANSC_106)
		   assegnoMantenimento:
            type: boolean
            description: I coniugi concordano l'assegno di mantenimento o divorzile
            example: false
           datiAssegnoMantenimento:
            type: string
            description: Nel caso esista l'assegno di mantenimento o divorzile      

	    - Aggiunti nuovi campi nel ModelMatrimonio come segue:
		   delegaConsolato:
			type: boolean
			description: Se il matrimonio ha avuto pubblicazioni in più comuni
			example: true 
          
        - Aggiunti nuovi campi nel ModelScioglimentoUnioneCivile come segue:
           assegnoMantenimento:
            type: boolean
            description: I coniugi concordano l'assegno di mantenimento o divorzile
            example: false
           datiAssegnoMantenimento:
            type: string
            description: Nel caso esista l'assegno di mantenimento o divorzile   
 			
        - Aggiunti nuovi campi nel ModelAnnotazioneModificativa come segue:
           nuovoNomeIntestatario:
            type: string
           vecchioNomeIntestatario:
            type: string
           vecchioCognomeIntestatario:
            type: string
            
            
	Nuovi casi d'uso gestiti (fare riferimento al mapping dei casi d'uso)
	 - Matrimonio con rito civile su delega del consolato
	 - Caso d’uso di servizio per annotazione modificativa
	 - Nuovo caso d'uso per annotazione modificativa cambio nome-cognome
	 - Separazione/divorzi: gestione assegno di mantenimento (https://github.com/italia/ansc/issues/554)
	

### Changed
    model_evento.yaml
        - Modificate descrizioni ed example dei seguenti campi in 				ModelAnnotazioneModificativa:
        			tipoModifica;
           		nuovoCognomeGenitore;
           		nuovoNomeGenitore;
           		vecchioCognomeGenitore;
           		vecchioNomeGenitore;
           		nuovoCognomeIntestatario;
           		
	Trasversale
		- La severity del controllo sul limite lunghezza numeroatto comunale a 5 viene abbassata a warning per il solo ambiente di preproduzione (https://github.com/italia/ansc/issues/566)           		
           		
### Fixed

	Servizi cooperativi
		- R009: Caso d'uso 1312 corretta richiesta verbale (https://github.com/italia/ansc/issues/530)     
		- R009: corretta incongruenza stato evento  (https://github.com/italia/ansc/issues/531)     
		- R010: corretta anteprima atto con annotazioni contestuali (https://github.com/italia/ansc/issues/539) 
		- R009: corretta validazione atto di morte con caso d'uso 2299 (https://github.com/italia/ansc/issues/529)
		- R001: corretto errore invio allegati firmati p7m - nome del File non corretto  
		(https://github.com/italia/ansc/issues/559)
		- R010: corretta anteprima atto matrimonio con officiante come ultimo firmatario
		(https://github.com/italia/ansc/issues/552)
		- R009: per i casi d'uso di cittadinanza indicati nella issue, è stata resa opzionale la data di formazione dell'evento collegato  (https://github.com/italia/ansc/issues/558)
		- R010 Anteprima: corrette diciture riportate nell'anteprima (https://github.com/italia/ansc/issues/555)
		
	Web Application
		- Corretto il profilo utente abilitato alla sola consultazione	 degli eventi
		- Corretta trascrizione decreto di cittadinanza (https://github.com/italia/ansc/issues/553)
		- [3.4.4.0.0.0] corretto accordo di modifica delle condizioni di separazione o divorzio (https://github.com/italia/ansc/issues/543)
		- Matrimonio civile fuori dalla casa comunale: corretta la minuta in merito alla data di formazione resa uguale alla data evento


## [1.21.4 - 18-12-2023]
           
### Removed
 
    Documentazione
	    - Casi d'uso obsoleti (https://github.com/italia/ansc/issues/547)


## [1.21.3 - 15-12-2023]
           
### Added
 
    Documentazione
	    - https://github.com/italia/ansc/blob/main/docs/Mapping_casi_uso/3_dec_use_case.csv (adesso contiene solo il mapping tra l'idusecase e il cod ansc del caso d'uso). (https://github.com/italia/ansc/issues/557)


## [1.21.2 - 14-12-2023]
           
### Fixed
 
	Servizi cooperativi
		- R009 Validazione residenza nella trascrizione nascita ai fini della generazione notifiche anagrafiche
		- R005 Regressione ricerca evento nei casi in cui era stata generata una notifica (https://github.com/italia/ansc/issues/536)
		
    Trasversale
		- "...provvedo alla trascrizione INTEGRALE del documento..." - sostituire la parola "INTEGRALE" con "PER RIASSUNTO" (https://github.com/italia/ansc/issues/545)
		- Generazione notifica di discordanza anagrafiche in caso di azzenza codice fiscale.
		
    Presa visione
       - Possibilità di firma digitale per più di un firmatario (https://github.com/italia/ansc/issues/540)

    Web application
       - Errore login temporaneo dell'applicazione web/otp (https://github.com/italia/ansc/issues/546)


## [1.21.1 - 13-12-2023]

### Fixed

	Servizi cooperativi
		- R006 Link presa visione inviato da servizi cooperativi di produzione corretto
		- Correttiva annotazioni automatiche casi d'uso adozione

    Notifiche angrafiche
       - Corretta la generazione notfica di una trascrizione di atto di nascita avvenuta all'estero di soggetto residente (https://github.com/italia/ansc/issues/540)

### Removed

    Documentazione
	    - Rimosso https://github.com/italia/ansc/blob/main/docs/Mapping_casi_uso/3_dec_use_case.csv (era usato solo fino a quando non tutti i casi d'uso erano stato rilasciati), fare riferimento adesso alla sola tabella 3 completa : https://github.com/italia/ansc/blob/main/docs/Decodifiche/3_dec_use_case.csv



## [1.21.0 - 11-12-2023]

### Added
     Aggiunta decodifica ANSC_105 relativa ala canale di comunicazione notifiche

### Changed 	
	R008_notifiche.yaml
		- Aggiunto campo in Response NotificheRicercaResponse come segue
            idcanalenotifica: # identifica il canale trasmissione notifica tramite decodifica ANSC_105 (DIGITALE/PEC)
            
### Fixed
 
	Servizi cooperativi
		- R002 /R010 Matrimonio estero: corretto luogo di matrimonio (idUseCase 331000 e 332000) (https://github.com/italia/ansc/issues/490)(https://github.com/italia/ansc/issues/510)
		- R005 ricerca intestatario: corretta ricerca per CF (https://github.com/italia/ansc/issues/518)
		- R008 ricerca notifiche: aggiunto idcanalenotifica nella response per discriminare tra notifiche destinate ad atti cartacei (da inviare via PEC) e notifiche destinate ad atti digitali (https://github.com/italia/ansc/issues/472)
		- R013 Annotazione di rettifica per annullamento: aggiunto controllo per atto già annullato
		- Caso d'uso di servizio annotazioni da altro comune: corretta la modifica della annotazione (https://github.com/italia/ansc/issues/517)
		- 12214300 Riconoscimento di nascituro: corretto template di presa visione (https://github.com/italia/ansc/issues/516)
		- R005: corretta ricerca evento per idcomune registrazione (senza intervallo temporale)
		- R002: corretti certificati atti di morte di tipo trascrizione(in assenza dello stato civile)
		- R005: Corretta visibilità annotazione automatica preproduzione (https://github.com/italia/ansc/issues/431)


## [1.20.1 - 05-12-2023]

### Fixed
 
	Servizi cooperativi
		- R006: Corretta regressione controllo sesso / data nascita firmatari (https://github.com/italia/ansc/issues/524)
		
   Web application
        - Nell'elenco allegati "visualizza pdf" è stato sostituito con "visualizza documento".


## [1.20.0 - 01-12-2023]

### Changed 	
	 model_evento.yaml
	   datiAnnotazioneModificativa in ModelEvento
	   		$ref: '#/components/schemas/ModelAnnotazioneModificativa
		
### Added

	Servizi cooperativi
		R005_consultazione_ansc.yaml
			- Aggiunto campo in CriteriRicercaEvento come segue:
	            flagRettifica: # flag per cercare l'ultima rettifica effettuata per l'evento (https://github.com/italia/ansc/issues/401)
	                  $ref: '#/components/schemas/CriteriRicercaEvento' 
				idComuneRegistrazione: # identificatore comune di registrazione
                  	  $ref: '#/components/schemas/CriteriRicercaEvento'	  
	      
	    R008_notifiche.yaml
	    	- Aggiunto nuovo servizio /notifiche/rifiuta/{version}
	    	- Aggiunto campo "descrizione" nella response NotificheRicercaResponse servizio /notifiche/ricerca/{version}
	    	    
		R013_rettifica_validazione:
			- Aggiunto nuovo servizio /annotazione/modificativa/validazione/evento/{version}

	Trasversale
		- Limite lunghezza numeroatto comunale a 5 (https://github.com/italia/ansc/issues/513)
		- Nuovo caso d'uso per annotazione modificativa cambio nome-cognome: codice caso d'uso 14750000
		- Gestione flusso di rifiuto annotazione / presa visione dell'evento da parte del comune di residenza
		- Messaggio servizi cooperativi per informazioni in caso di assistenza, es. {"code": "110527","severity": "I","text": "Informazioni sull'operazione da fornire in caso di assistenza : data:xxxx , idOperazione:yyyy"}
		
	
### Fixed
 
	Trasversale
		- Adeguata ora presente sugli atti da UTCnel timezone corrente
		- Annotazioni automatiche matrimonio/unione civile: da differenziare per i due coniugi (https://github.com/italia/ansc/issues/406)
		- Inserito controllo sulla lunghezza del numero comunale (ammessi massimo 5 caratteri)
		- R006: corretta firma dichiaranti cartaceo errore corrispondenza firmatari (https://github.com/italia/ansc/issues/449)
		- R009: corretta validazione IdUseCase 14400000 errore: "Evento su cui apporre l'annotazione non valorizzato" (https://github.com/italia/ansc/issues/440)
		- R009 SEP_DIV_002: verificata obbligatorietà tipoAccordo (https://github.com/italia/ansc/issues/468)
		- R009: Caso d'uso 348000 corretta mancata conferma di separazione o divorzio (Sep_Div_008)(https://github.com/italia/ansc/issues/476)
		- R008: corrette notifiche a seguito di divorzio (https://github.com/italia/ansc/issues/434)
		- R009: corretta validazione caso d'uso Citt_046, Stato Ente e Anagrafica Consolato non visualizzate (https://github.com/italia/ansc/issues/448)
		- R009: caso uso servizio per matrimonio con rito civile resa pubblicazione opzionale (https://github.com/italia/ansc/issues/542)
		- R005: aggiunto come ulteriore filtro di ricerca il comune di registrazione evento
		e	Web Application
		- corretta minuta dell'atto formula di chiusura: dicitura l’atto è stato letto agli “intervenuti” al plurale, o al singolare se è intervenuta solo una persona.
		- aggiunta nuova funzione 'Altri servizi' : funzionalità acquisizione data validità a valle della registrazione dell'evento
		- Corretto errore "presa visione" con accesso tramite SPID (https://github.com/italia/ansc/issues/488)


## [1.19.6 - 24-11-2023]

### Fixed

	Trasversale
		- Corretta la generazione dei certificati: aggiunta la gestione dei caratteri speciali per il campo evento.trascrizioneMatrimonio.testoLibero


## [1.19.5 - 23-11-2023]

### Fixed

	Web Application
	   - R009 Matrimoni estero (idUseCase 331000 e 332000): aggiunto luogo di matrimonio (https://github.com/italia/ansc/issues/490)
	   
	Trasversale
		- Caso d'uso di servizio trascrizione [1.3.9.9] [2.2.9.9] [3.3.9.9.9.9] [5.2.9.9.9] [4.3.9.9.9.9]: resi opzionali i dati anagrafici di residenza e nazionalità per l'intestatario


## [1.19.4 - 22-11-2023]

### Fixed

	Presa visione
	   - Accesso SPID presa visione preproduzione. (https://github.com/italia/ansc/issues/488)


## [1.19.3 - 21-11-2023]

### Fixed

	Trasversale 
		- E' stato aumentato il tempo di completamento di un atto a 336 ore (14 giorni).
		- Limite upload allegati innalzato a 10MB.
		- Accettato formato p7m per gli allegati.


## [1.19.2 - 20-11-2023]


### Fixed
	Web app
		- Negoziazione assistita: corretta obbligatorietà allegati in base alla scelta del tipo provvedimento
		- 319999 Caso d'uso di servizio (matrimoni con rito civile): aggiunta la seconda pubblicazione in caso di pubblicazioni in più comuni
		- Trascrizione di un decesso proveniente dal Consolato: corretta la minuta dell'atto
		
	Trasversale 
		- E' stato aumentato il tempo di completamento di un atto a 36 ore


## [1.19.1 - 16-11-2023]

### Fixed

     Web app
		- [2.2.9.9] Caso d'uso di servizio (trascrizioni di morte): aggiunti dati di decesso
		- Trascrizione matrimonio con caso d'uso di servizio: resi emissibili i certificati
		
	 Trasversale
		- Anteprima per presa visione: eliminata data presa visione
		- Gestione comuni non validi alla data: da utilizzare idComuneNascita = 0 e nomeComuneNascita libero per indicare un comune di nascita non valido alla data


## [1.19.0 - 14-11-2023]

### Added
	
    Versione
       - Aggiunta nuova versione 100006
    model_evento.yaml
       - Aggiunti campi nel ModelSeparazione come segue:
          luogoEventoMatrimonio:
              $ref: '#/components/schemas/ModelLuogo' 
            officianteEventoMatrimonio:
               type: string
               description: Officiante che ha effettuato il matrimonio
               example: 'Gianni Rossi Parroco'
       - Aggiunto campo nel ModelLuogo come segue:
	  comuneEstero: 
            type: string
            description: Comune Estero
            example: 'Londra'   
            

### Fixed

     Web app
		- caso d'uso [342000] Accordo di scioglimento (o di cessazione degli effetti civili) del matrimonio: aggiunto il luogo del matrimonio e l'officiante
		- Ricerca soggetto collegato/intestatario per CF
		- Corretta minuta dell'atto in merito ai comuni pregressi

	Servizi cooperativi
		- R009 caso d'uso [342000] Accordo di scioglimento (o di cessazione degli effetti civili) del matrimonio: aggiunto il luogo del matrimonio e l'officiante
		
	Trasversale
		- Caso Uso 1312 Trascrizione di atto di nascita avvenuta all’estero su richiesta di chi ha interesse alla trascrizione: corretta obbligatorietà anagrafica soggetti


## [1.18.5 - 13-11-2023]

### Fixed

     Web app
		- corretta anomalia metadati mancanti.
		- ricerca soggetto intestatario: resi liberi i campi nazionalità e residenza.
	
	 Sistema
	   - Tuning performance

## [1.18.4 - 09-11-2023]

### Fixed

     Web app
		- L'ultimo numero comunale suggerito ora è quello dell'ultimo numero già usato per una registrazione.
		- Nella composizione dell'atto, in caso di nessun ruolo particolare dell' Ufficiale di stato civile, la dicitura predefinita diventa 'per delega ricevuta'.
		- Trascrizione matrimonio dall'estero richiesta da consolato: minuta non corretta (use case 332000).
		- Annotazione di rettifica evento: resi editabili campi generalità soggetto
		- Corretto controllo anagrafico in caso di inserimento soggetto già presente in ANSC
		- Corretta ricerca soggetto intestatario senza nazionalità: reso editabile nazionalità e residenza


## [1.18.3 - 07-11-2023]

### Fixed

     Casi d'uso
		- Corretta annotazione inserita con  caso d'uso di servizio


## [1.18.2 - 06-11-2023]

### Changed

    Web Application
		- Gestione data di validità nel pannello di firma USC: al fine di evitare la dimenticanza della data di validità anagrafica, questa è stata resa obbligatoria a meno che non viene esplicitamente dichiarato che l'evento non necessita di 'Nessuna comunicazione anagrafica'
		
	Servizi cooperativi
		- [R007] servizio di firma: aggiunto messaggio di warning in caso data validità null 


### Fixed

	Trasversale
		- Corretta l'annotazione automatica generata da trascrizione di cittadinanza
		
	Web Application
		- Matrimonio rito religioso: corretta minuta nel caso in cui non vengano popolati tutti i dati degli atti di nascita dei coniugi
		- Trascrizione di un matrimonio estero su richiesta dell'interessato: corretta la minuta in merito al richiedente


## [1.18.1 - 05-11-2023]

### Fixed

    Anteprima / Certificazione
		- Anomalia generazione anteprime / certificati per gli eventi di Matrimonio, sia web application che servizi (https://github.com/italia/ansc/issues/454)


## [1.18.0 - 03-11-2023]

### Added

    Versione
		- Aggiunta nuova versione 100005
	model_evento.yaml
        - Aggiunto campo nel ModelNegoziazioneAssistita come segue:
            ricezioneAtto:
              type: string
              description: Chi ha inviato l'accordo di negoziazione' (decodifica ANSC_103)
        - Aggiunto campo nel ModelSeparazione come segue:
            tipoProvvedimentoSeparazione:
              type: string
              description: Provvedimento di separazione (decodifica ANSC_104)
              example: '1'
            
    Decodifica
      - Aggiunta tabella decodifica ANSC_103 DEC_RICEZIONE_ATTO Ricezione Atto
      - Aggiunta tabella decodifica ANSC_104 DEC_PROVVEDIMENTO_SEPARAZIONI Provvedimento di separazione

### Fixed

    Servizi cooperativi
        - R001 / R006 Allineato controllo tipo allegato per upload allegati e firma dichiaranete a quanto avviene sulla web app (tipologia accettate e congruenza con tipo dichiarato)
        - R001 / R006 TRASCR_MATR_002: rimosso campo tipoDichiarazione.    
        - R009 TRASCR_MATR_002: rimosso campo tipoDichiarazione.
        - R005 Consultazione ANSC Intestatario: corretto errore per dati mancanti (https://github.com/italia/ansc/issues/324) 
        - R009 Caso d'Uso Sep_Div_005: gestione unico provvedimento inviato da avvocato (https://github.com/italia/ansc/issues/414) 
        - R009 Caso d'uso Sep_Div_005: corretta formula per una imprecisione presente sul formulario (https://github.com/italia/ansc/issues/436)
        - R009 Sep_Div_002: corretta gestione autorità giudiziale (https://github.com/italia/ansc/issues/430)
        - R012 Firma elettronica dichiarante: corretta presa visione  (https://github.com/italia/ansc/issues/405)
        - R002 Estratti integrali unioni civili: corrette etichette con Unito/a civilmente 1 e Unito/a civilmente 2 
        
     Web Application
     	 - Dichiarazioni di nascita: corretta formula nella minuta per bambino presentato/non presentato
     	 

## [1.17.2 - 02-11-2023]

### Fixed

	Servizi cooperativi
       - R002 servizio certificazione, in caso di data nascita richiedente assente si verificava un errore 500.
       

## [1.17.1 - 31-10-2023]

### Fixed

	Servizi cooperativi
		- Gestione durata OTP per servizi cooperativi (https://github.com/italia/ansc/issues/442) (Inoltre il messaggio 404002 - 'Nessun dato associato all’utente' viene sostituito da 404003 -  'Codice OCP non trovato per l'utente')
       - R901 servizio decodifiche
       - Anteprima in caso di decodifiche non presenti       
       
    Web application
       - Gestione verifica certificati qrcode corretto  
       
	Decodifica
       - Aggiornamento date fine validità versioni (https://github.com/italia/ansc/issues/437)

## [1.17.0 - 30-10-2023]

### Added

	Certificati (sia web app che servizio R002)
		- Sigillo del ministero
		- Link per verifica qrcode
		- Generazione dei certificati in formato PDF/A

### Changed

    Servizi cooperativi
		- R002: Il nome del file restituito ora è uguale alla proprietà della risposta 'idCertificato' con aggiunta estensione pdf

## [1.16.0 - 26-10-2023]

### Deprecated
	model_evento.yaml
		- Reso deprecato elemento cognomeOfficiante in ModelUnioneCivile 
		- Reso deprecato elemento nomeOfficiante in ModelUnioneCivile

### Added
    Versione
		- Aggiunta nuova versione 100004

	model_evento.yaml
		- Aggiunto campo nel ModelUnioneCivile come segue:
            officianteEvento: # Chi ha officiato unione civile
                  $ref: '#/components/schemas/ModelSoggetto'  
        - Aggiunto campo nel ModelSeparazione come segue:
            dataEventoMatrimonio:
            type: string
            format: date
            description: Data alla quale viene effettuata il matrimonio
            example: '2002-07-02'
            
### Fixed 

	Servizi cooperativi
		- R009 Sep_Div_001/Sep_Div_002 Accordo di separazione/scioglimento: aggiunta data evento matrimonio, richiesta nella formula
		- R002: certificati di morte, inseriti i dati dei coniugi nel caso il deceduto risulti coniugato, vedovo o divorziato
		- R009: corretto controllo su soggetto intestatario (https://github.com/italia/ansc/issues/429)
		
		
	Web Application
		- Sep_Div_001/Sep_Div_002 Accordo di separazione/scioglimento: corretta la minuta, gestita la frase relativa agli allegati in caso di allegati non presenti.Gestita assenza degli avvocati nella formula di chiusura.
		- Sep_div_001/Sep_div_002/Sep_div_003/Sep_div_004/Sep_div_008: corretta mancanza dei coniugi come firmatari
		

	Mapping casi d'uso	
		- Sep_div_005: modificata obbligatorietà degli allegati; Allegato id 48 "Atto di Matrimonio" reso facoltativo, Allegato id 19 "Decreto del tribunale" reso obbligatorio,Allegato id 51 " Certificazione come da articolo 5 del Decreto Legge n. 132/2014 convertito con Legge 10.11.2014 n.162" reso facoltativo,Allegato id 36 " Nulla osta" reso obbligatorio
		


## [1.15.2 - 23-10-2023]

### Fixed 

	Servizi cooperativi
		- R009 matrimoni: aggiornamento obbligatorietà dei dati anagrafici del soggetto officiante nei matrimoni; sono stati resi opzionali tutti i campi dell'anagrafica tranne nome e cognome (https://github.com/italia/ansc/issues/422)
		- R006 firma dichiarante con lista firmatari: il servizio richiede necessariamente i dati anagrafici  con cui il soggetto è stato registrato (es. se il coniuge è stato registrato con nome, cognome, sesso e data di nascita, questi campi devono essere trasmessi anche nel servizio R006; se l'officiante è stato registrato solo con nome e cognome, il servizio R006 dovrà essere invocato tramsettendo solo nome e cognome)
		- R009: matrimoni, corretta la validazione relativa agli intestatari (https://github.com/italia/ansc/issues/423)
		- R009: 51105 corretto acquisto automatico di cittadina straniera che si sposa con cittadino italiano fino al 27 aprile 1983 (https://github.com/italia/ansc/issues/407)
		- R009: Sep_Div_005 corretto Accordo di negoziazione assistita (https://github.com/italia/ansc/issues/377)


### Added 		
	Decodifica
	 - Aggiornata tabella 96_dec_motivo_recupero


## [1.15.1 - 18-10-2023]

### Fixed 

	Servizi cooperativi
		- R009: Fix verifica residenza intestatario, errore 500 (https://github.com/italia/ansc/issues/419)
		- R901: Allineato vallore id 51 tabella 9_dec_tipo_allegato (https://github.com/italia/ansc/issues/420)
		
 	Web Application
		- Chiarimento: scaricamento atto dopo la firma USC : Emissione certificati (https://github.com/italia/ansc/issues/418)


## [1.15.0 - 16-10-2023]

### Deprecated
	model_evento.yaml
		- Reso deprecato elemento cognomeOfficiante in ModelMatrimonio 
		- Reso deprecato elemento nomeOfficiante in ModelMatrimonio
		- Reso deprecato elemento conTestimoni in ModelEvento
		- Reso deprecato elemento variazioni in ModelEvento
		
### Added 
    Decodifica
    	- Aggiunta tabella decodifica ANSC_85 DEC_PROVVEDIMENTO_CAMBIO_COGNOME
    
	model_evento.yaml
		- Aggiunto campi nel ModelMatrimonio come segue:
        officianteEvento: # Chi ha officiato il matrimonio 
              $ref: '#/components/schemas/ModelSoggetto'
		- Aggiunto campo flagAnnotazioneNonCertificabile che indica se l'annotazione è certificabile o meno
		
### Changed 
	ModelEvento
        - aggiornata descrizione ed example per elemento ausilioInterprete in 
        - aggiornata descrizione con specifica nuova decodifica (decodifica ANSC_85) per campo provvedimentoCambioCognome
        - aggiornata descrizione campo e corretto l'example per idProvinciaResidenza
        - aggiornata descrizione campo e corretto l'example per comuneCertificatoCostituzione
        - aggiornata descrizione campo soggettoImpedimentoCivile specificando la decodifica (decodifica ANSC_95)
        
		- ModelDocumentoRiconoscimento :
					tipologiaDocumento: (aggiunto la decodifica ANSC_25 nella description come documentazione, anche l'example abbiamo messo un esempio corretto dei 					valori da utilizzare)
		   - dataInizioValidita:
			   type: string
               description: Tipologia di documento utilizzato per il riconoscimento (decodifica ANSC_25).
               example: "1"        

	Servizi cooperativi
		- R013_rettifica_validazione.yaml: campo eventoModificato in ValidazioneRettificaEventoRequest per rettifiche di annullamento non obbligatorio

	Documentazione
		- [NotaProcessoAnnotazioniAndQuickCoopServiceFlow 1.2.0](Note/NotaProcessoAnnotazioniAndQuickCoopServiceFlow/NotaProcessoAnnotazioniAndQuickCoopServiceFlow.pdf)

### Fixed 

	Servizi cooperativi
		- R009: Gestione certificabilità per annotazioni contestuali e per caso d'uso libero annotazioni
		- R010: corretto errore dati in ingresso non corretti (https://github.com/italia/ansc/issues/403)
		- R009 IDUseCase 51103 Citt_011: corretta errata validazione campo tipologiaDocumento (https://github.com/italia/ansc/issues/382)
		- R011: aggiunto controllo per evitare cancellazione atto in stato FIRMATO USC (https://github.com/italia/ansc/issues/408)
		- R009 IDUseCase 439999 Trascr_UnCiv_999: corretto refuso nel tracciato (https://github.com/italia/ansc/issues/388)
		- Gestione stati pregressi non validi alla data e/o non più esistenti: da utilizzare il codice 200 in idStatoNascita e trasmettere il nome dello stato pregresso
		- R009 caso d'uso 11124100: corretta dichiarazione tardiva di filiazione nel matrimonio resa dal procuratore del padre all'USC di filiazione di bimbo nato morto (https://github.com/italia/ansc/issues/391)
		- R009: corretta obbligatorietà di comune e provincia in UC 1.3.1.1 Trascrizione di atto di nascita avvenuta all’estero su richiesta dell’autorità diplomatica o consolare
		- R013: correttaannotazione di rettifica di tipo annullamento (https://github.com/italia/ansc/issues/384)
		- R010/R006: Firma officiante modalità cartacea su atti di matrimonio (https://github.com/italia/ansc/issues/380)
		- R009: UC Matrimonio, gestione officiante come soggetto firmatario
		- R009: IDUseCase 433000 e 434000 corretti tracciati (https://github.com/italia/ansc/issues/387)
		- R005: corretta consultazione evento annotazione (https://github.com/italia/ansc/issues/371) (https://github.com/italia/ansc/issues/400)
		- R009: corretta validazione caso uso 345000 per Trascrizione della convenzione di negoziazione assistita (https://github.com/italia/ansc/issues/404)


## [Versione 1.14.1 - 11-10-2023]

### Added

	Mapping casi d'uso	
		- Rico_Matr_999 (https://github.com/italia/ansc/issues/374)

### Fixed 

	Servizi cooperativi
		- R001: corretta anomalia upload allegati (https://github.com/italia/ansc/issues/398)




## [Versione 1.14.0 - 09-10-2023]

### Added

    Web Application
       -	Revisione copy dei messaggi relativi alla formazione atti anomali
       -	Aggiunto il controllo relativo all'eta' dichiarante in base alla tipologia dell'atto e del caso d'uso
	Versione
		- Aggiunta nuova versione 100003 (1.14.X)
	Mapping casi d'uso
		- La colonna delle condizioni per cui si può ignorare un campo, ora non ha più le parentesi graffe (ad esempio '{evento.campo,=,2}' 'diventa evento.campo,=,2')
		
		
    model_evento.yaml
		- Aggiunto campi nel ModelMatrimonio come segue:
        tipoAssistenteSposo :
          type: string
          description: Tipo assistenza minori (decodifica ANSC_51) 
          example: "0" 
        tipoAssistenteSposa :
          type: string
          description: Tipo assistenza minori (decodifica ANSC_51) 
          example: "0"   
        padreSposo: # Generalita'  padre Sposo
          $ref: '#/components/schemas/ModelSoggetto'
        padreSposa: # Generalita'  padre Sposa
          $ref: '#/components/schemas/ModelSoggetto'  
        madreSposo: # Generalita' madre Sposo
          $ref: '#/components/schemas/ModelSoggetto'
        madreSposa: # Generalita' madre Sposa
          $ref: '#/components/schemas/ModelSoggetto'   
        assistenteLegaleSposo: # Generalita' assistenteLegale Sposo
          $ref: '#/components/schemas/ModelSoggetto'
        assistenteLegaleSposa: # Generalita' assistenteLegale Sposa
          $ref: '#/components/schemas/ModelSoggetto'             
        nominaAssistenteLegaleSposo: # Provvedimento di nomina del tutore/procuratore speciale
          $ref: '#/components/schemas/ModelEnteDichiarante'  
        nominaAssistenteLegaleSposa: # Provvedimento di nomina del tutore/procuratore speciale
          $ref: '#/components/schemas/ModelEnteDichiarante'   
	model_evento.yaml
		- Aggiunto campo tipoProvvedimento nel ModelNegoziazioneAssistita come segue:
			 tipoProvvedimento:
          type: string
          description: Tipo provvedimento (decodifica ANSC_99)
          example: "1"
		  
	Decodifica
		- Aggiunta decodifica ANSC_99 Riguardante al Tipo Provvedimento
		
	Servizi cooperativi
		-Aggiunta validazione stringente dei payload trasmessi rispetto alle specifiche dichiarate negli yaml
		- R901_config_decodifica: aggiunto servizio di consultazione comuni aderenti ad ANSC /config/decodifica/data_adesione/{version}; 
		- possibile ottenere l'elenco completo dei comuni con l'id decodifica 110
		- Aggiunto il controllo relativo all'eta' dichiarante in base alla tipologia dell'atto e del caso d'uso
		- R008: aggiunto il servizio /notifiche/ricerca-notifiche-anpr/{version} per la consultazione delle notifiche anagrafiche generate da ANSC per un evento di stato civile
	
	Servizi cooperativi ANPR
	 	- aggiunta idNotifica alla testata richiesta delle notifiche relative alle predisposizioni anagrafiche provenienti da ANSC
	 	
		
### Changed 
		Cambio del formato date a date-time nei seguenti campi nel ModelNotifica:
		   - dataInizioValidita:
			  type: string
			  format: date-time
			  description: data di inizio validita
		   - dataFineValidita:
			  type: string
			  format: date-time
			  description: data di fine validita

### Fixed 
	Servizi cooperativi
		- R013: corretto errore 'Dati in ingresso non corretti' (https://github.com/italia/ansc/issues/396)
		- [R009] Caso 12226203: corretto Riconoscimento infraquattordicenne
		(https://github.com/italia/ansc/issues/342)
		- [R009] IDUseCase 339999 Trasc_Matr_999: aggiunto comuneEstero obbligatorio (https://github.com/italia/ansc/issues/368)
		- Certificati ed estratti di morte: aggiunti data di nascita e luogo di nascita se presente (https://github.com/italia/ansc/issues/355)
		- Firma Dic / Firma Usc: matrimoni (idUseCase 331000) corretti Messaggi
		(https://github.com/italia/ansc/issues/350)
		- R009: aggiunto dettaglio nell'eventuale errore restituito
		(https://github.com/italia/ansc/issues/351)
		- R009 ID UseCase 2213 (Morte_007): corretta errata segnalazione
		(https://github.com/italia/ansc/issues/363)
		- R008: corretto formato delle date dell'oggetto ModelNotifica
		(https://github.com/italia/ansc/issues/361)
		- R009: caso d'Uso 345000 corretta Trascrizione Negoziazione Assistita
		(https://github.com/italia/ansc/issues/150)
		- [R009] corretta gestione Assistenza Minori nei matrimoni
		(https://github.com/italia/ansc/issues/268) (https://github.com/italia/ansc/issues/257)
		(https://github.com/italia/ansc/issues/271)
		(https://github.com/italia/ansc/issues/286)
		- R013: corretta restituzione IdAnsc
		(https://github.com/italia/ansc/issues/347)
		- R009: Citt_025 corretta revoca dell'adozione per il fatto dell'adottante, rinuncia espressa cittadinanza entro un anno dalla revoca adozione - aggiunto il controllo di validità non bloccante sulla data sentenza (che dovrà essere entro 1 anno dalla data di sistema).
		- [R009]: UC matrimonio corretta configurazione rigettoOpposizione' e 'estintaOpposizione
		(https://github.com/italia/ansc/issues/356)
		- [R009] IDUseCase 342000-Sep_Div_002: corretta la verifica su tipoAccordo
		(https://github.com/italia/ansc/issues/375)
		- [R009] UseCase 11117000/11114200: corretti problemi con l'allegato della Procura della madre (https://github.com/italia/ansc/issues/376)
	
	 Mapping Casi d'uso
	 	- Matrimoni: corretta "Condizioni obbligatorietà" su difetto di età e impedimento parentela (https://github.com/italia/ansc/issues/327)
	 	
	Web App
		- Matrimonio: Rito religioso corretta minuta atto
		- Consultazione atto: aggiunta la visualizzazione dell'id ansc del soggetto intestatario


## [Versione 1.13.1 - 29-09-2023]

### Fixed 
	Mapping casi d'uso
		- In tutti i mapping, corretta la colonna di obbligatorietà (ora l'intestazione è differente per gli allegati e le sezioni) 	(https://github.com/italia/ansc/issues/367)


## [Versione 1.13.0 - 22-09-2023]

### Added 
	Processo
		- Gestione dell'approvazione delle notifiche per le proposte di annotazioni /presa visione dell'ato da parte del comune di residenza

### Added
	Decodifica
		- Aggiunta tabella decodifica ANSC_20 Ente che ha rilasciato il documento di riconoscimento
		- Aggiunta tabella decodifica ANSC_84 Stato Cittadinanza
		- Aggiunta tabella decodifica ANSC_101 Genere Notifiche
		- Aggiunta tabella decodifica ANSC_102 Stato Flusso Notifiche
	
	R008_notifiche.yaml
		- Aggiunto campo id nel ModelNotifica come segue:  
			id:
         	type: string
          	description: Identificativo univoco della notifica
    
	Web Application
    	- Aggiunta consultazione delle annotazioni 'da confermare'
	
### Fixed

	model_evento.yaml
		- Corretta decodifica genitoreConCittadinanza in ModelTrascrizioneCittadinanza (ANSC_88)
		- Esplicitata decodifica tipoEventoCittadinanza in ModelDatiEventoCittadinanza (ANSC_84)
		- Reso deprecato elemento ufficialeStatoCivile (https://github.com/italia/ansc/issues/348)
		
	Servizi cooperativi
		- R009: corretta validazione caso 1343 (https://github.com/italia/ansc/issues/341)
		- R009: corretto caso 345000 - Trascrizione della convenzione di negoziazione assistita (https://github.com/italia/ansc/issues/326)
		- R009: corretta validazione casi d'uso di trascrizioni da estero (https://github.com/italia/ansc/issues/325)
		- Citt_002: corretta configurazione errata (https://github.com/italia/ansc/issues/314)
		- R009: corretta validazione caso d'uso 1365 (https://github.com/italia/ansc/issues/336)
		- R012 - Servizio di pooling: corretta decodifica degli stati della presa visione, mancante (https://github.com/italia/ansc/issues/272)
		- R009: Citt_011 corretto pattern errato su documentoRiconoscimento (https://github.com/italia/ansc/issues/229) (https://github.com/italia/ansc/issues/244) (https://github.com/italia/ansc/issues/315) (https://github.com/italia/ansc/issues/343)
		- R002: scaricamento atto dopo la firma USC senza lista sul PDF (https://github.com/italia/ansc/issues/178)
		- R009: corretta validazione atto di cittadinanza per "evento.motivoRecupero" (https://github.com/italia/ansc/issues/258) (https://github.com/italia/ansc/issues/331)
		- R006: corretto errore "Non sono stati recuperati firmatari per i dati inseriti" (https://github.com/italia/ansc/issues/321)
		- R009: corretto caso 2.2.1.2 Richiesta trascrizione atto di morte all'estero richiesto da privati con istanza scritta (https://github.com/italia/ansc/issues/319)
		- R005: corretta ricerca intestatario attraverso idAnpr (https://github.com/italia/ansc/issues/328)
		- R001: corretta verifica stato allegato (https://github.com/italia/ansc/issues/345)
		
	Web Application
		Matrimonio religioso: corretta minuta dell'atto
		Sciogl_UnCiv_002 (4.4.2.0.0.0): corretta minuta dell'atto
		Consultazione atto: aggiunto identificativo nazionale 
		Casi d'uso con presenza comparente: aggiunta firma anche per il comparente laddove presente
		Eliminata la dichiarazione sostitutiva in caso di presentazione della dichiarazione da parte di ostetrica/sanitario
		UC Trascr_024 : corretta minuta dell'atto
		
	Decodifica
		- Corretta tabella dec_tipo_allegato(https://github.com/italia/ansc/issues/346)
		
	Documentazione
		- corretta descrizione della colonna 'Condizioni obbligatorietà' (https://github.com/italia/ansc/issues/349)
	
### Changed 
	R008_notifiche.yaml
		- Aggiunto servizio di conferma notifiche di proposte di annotazione/presa visione evento (/notifiche/conferma/{version})
	 	- Aggiunti i seguenti campi nella response del servizio /notifiche/getNotificheByEvento/{version}:
	 		idStatoFlussoNotifiche:
          description: Stato flusso della Notifica 1=DA APPROVARE 2=APPROVATA (decodifica ANSC_102)
        	idGenereNotifiche:
          description: Genere di Notifica 1=Annotazione 2=Trascrizione (decodifica ANSC_101)
		- Aggiunti i seguenti campi nella response e nella request del servizio /notifiche/ricerca/{version}:
			idStatoFlussoNotifiche:
          description: Stato della Notifica 1=DA APPROVARE 2=APPROVATA (decodifica ANSC_102)
          type: string
          example: '1'
         idGenereNotifiche:
          description: Genere di Notifica 1=Annotazione 2=Trascrizione (decodifica ANSC_101)
          type: string
          example: '1'


## [Versione 1.12.1 - 11-09-2023]

### Fixed

	Servizi Cooperativi 
		- R005 Ricerca: fix data di nascita (https://github.com/italia/ansc/issues/330)


## [Versione 1.12.0 - 05-09-2023]

### Added
	Decodifica
		- Aggiunta tabella decodifica ANSC_98 Tipo riconoscimento Sentenza
		(https://github.com/italia/ansc/issues/311) (https://github.com/italia/ansc/issues/307)
		- Aggiunta tabella decodifica ANSC_88 Tipo Genitore Cittadinanza
		
		
### Fixed

	Servizi Cooperativi 
		- R009_validazione: Riabilitato controllo dataNascita dichiarazioni tardive
		- R009 Validazione - Negoziazione Assistita (345000): Corretti allegati obbligatori (https://github.com/italia/ansc/issues/227)
		- R009 validazione caso d'uso di servizio (trascrizioni nascita)e cittadinanza: corretta obbligatoriet� evento.motivoRecupero obbligatorio
		(https://github.com/italia/ansc/issues/248) (https://github.com/italia/ansc/issues/258)
		- Citt_004: corretto errore bloccante su caso 52143 atti di cittadinanza
		(https://github.com/italia/ansc/issues/266)
		-  Trascrizione Unione Civile dall'estero: corretto titolo formule (https://github.com/italia/ansc/issues/293)
		- Citt_011: corretto usecase 51103 (https://github.com/italia/ansc/issues/308)
		- R010 Anteprima: corretto errore "Dati in ingresso non corretti" (https://github.com/italia/ansc/issues/285)
		- Corretti allegati obbligatori per caso d'uso Citt_09 (https://github.com/italia/ansc/issues/217)
		- Servizio R005 - Descrizione errata per l'idComunale
		(https://github.com/italia/ansc/issues/274)
		- Mapping caso d'uso 12214300 (Rico_003) 
		(https://github.com/italia/ansc/issues/283)
		- Mapping caso d'uso 12221122 (Rico_004)
		(https://github.com/italia/ansc/issues/284)
		- RICO_013: corretta descrizione allegato obbligatorio
		(https://github.com/italia/ansc/issues/305)
		- Dic_Nasc_080: configurazione obbligatoriet� allegati in usecase 
		(https://github.com/italia/ansc/issues/193)
		-R010 (Anteprima) e R002 (Certificazione): download pdf con i dettagli dell'atto 
		(https://github.com/italia/ansc/issues/223) (https://github.com/italia/ansc/issues/275)
		- Casi d'uso di servizio di tipo trascrizione : aggiunti come opzionali gli estremi dell'atto originale
		
		
	model_evento.yaml
		- Corretta decodifica genitoreConCittadinanza in ModelTrascrizioneCittadinanza (ANSC_88)
		
		
	Decodifica
	- Corretti Usecase 51101 e 52112 di Cittadinanza con descrizioni duplicate
		(https://github.com/italia/ansc/issues/302)
	
### Changed 
	R005_consultazione_ansc.yaml
		- cambiata la descrizione del campo IdComunale da "Numero Comunale" a "Numero Comunale dell'Atto"


## [Versione 1.11.4 - 30-08-2023]

### Fixed
	
	Changelog versione 1.11.0
		Specificiato cosa indicare nel nuovo campo OTP della web app [In ambiente di preproduzione è possibile usare un valore qualsiasi, es '20220730', in produzione sarà necessario inserire l'otp restituito generato dalla propria firma remota : app mobile o token fisico.]

### Added

	Mapping Casi d'uso
		-Aggiunto mapping casi d'uso Dic_Nasc_019, Dic_Nasc_057, Sep_Div_008 (https://github.com/italia/ansc/issues/297)


## [Versione 1.11.3 - 18-08-2023]

### Fixed

	Servizi Cooperativi 
		- R009_validazione: Disabilitato controllo dataNascita dichiarazioni tardive (https://github.com/italia/ansc/issues/298)


## [Versione 1.11.2 - 17-08-2023]

### Fixed

	Servizi Cooperativi 
		- R901_config_decodifica: La tabella ANSC_97 non veniva restituita correttamente (https://github.com/italia/ansc/issues/294)


## [Versione 1.11.1 - 11-08-2023]

### Fixed

    Decodifica
		- Tabella ANSC_95 rinominata da 95_dec_tipo_impedimento a 95_dec_soggetto_impedimento_civile (https://github.com/italia/ansc/issues/289)	

### Changed 
	
	 Piano di test
		- Rimossi Matr_015 e Matr_016 dal piano di test (https://github.com/italia/ansc/issues/290)	


## [Versione 1.11.0 - 10-08-2023]

### Fixed

	model_evento.yaml
		- Modificata descrizione (corretta decodifica ANSC_42) e example per attributo genitoreConCittadinanza in ModelTrascrizioneCittadinanza
		- Modificata descrizione per attributo intestatari in ModelEvento per indicare che in caso di matrimonio l'elemento 0 e' lo sposo e l'elemento 1 e' la sposa
		- OpenAPI - Aggiornata decodifica ANPR_26 mancante sull'attributo idAnagraficaConsolato (https://github.com/italia/ansc/issues/256)	
		- Aggiunta decodifica ANSC_20 mancante sulla description sull'attributo rilasciatoDa
		- Aggiunta decodifica ANSC_01 mancante sulla description sull'attributo tipologia presente sul ModelAttoCollegato
		- Reso deprecato elemento AssistenzaMinori in ModelRegimePatrimoniale
		- Reso deprecato elemento ruolo in ModelDatiDichiarante
		
	Servizi Cooperativi 
		- R009_validazione: eliminata obbligatorietà indirizzo e numero Civico per luogo celebrazione su UseCase 321311 (https://github.com/italia/ansc/issues/245)(https://github.com/italia/ansc/issues/184)
		- R009_validazione: gestione data decorrenza, reso obbligatorio specificare ora decorrenza, minuto decorrenza e motivo recupero solo se data decorrenza è diversa da data formazione
		- R005: correttoa la consultazione annotazioni (https://github.com/italia/ansc/issues/159)
		- R002: corretto certificazione soggetto intestatario (https://github.com/italia/ansc/issues/163)
		- R009_validazione
			-corretto UC Matr_004 (https://github.com/italia/ansc/issues/233)
			-corretto UC 11111000 (https://github.com/italia/ansc/issues/228)
			-corretto Rico_013 e Rico_016 (https://github.com/italia/ansc/issues/207)
			-corretto UC Citt_002 (https://github.com/italia/ansc/issues/265)
			-corretto UC manifestazione volontà scioglimento (https://github.com/italia/ansc/issues/226)
			-corretto Citt_021 e Citt_022 (https://github.com/italia/ansc/issues/261)
			-corretto Citt_023 e Citt_025 (https://github.com/italia/ansc/issues/262)
			-corretto UC matrimoni 312111 (https://github.com/italia/ansc/issues/225)
			-corretto UC unioni civili -corretto Citt_021 e Citt_022 (https://github.com/italia/ansc/issues/216)
			-corretto Citt_011 (https://github.com/italia/ansc/issues/229) (https://github.com/italia/ansc/issues/244)
			-corretto Citt_004 (https://github.com/italia/ansc/issues/260)
		

### Added 
	
	 Gestione retocompatibilità
		- Note Gestione Retrocompatibilità (Note/NotaRetrocompatibilitaServizi/index.md)
		- R009_validazione.yaml: gestione idVersione per applicare la validazione relativa alla versione del sistema specificata (Rif. nota di rilascio XXXX)
		
	 Controlli
	 	- aggiunto controllo sull'intestatario per evitare di inserire soggetti con anagrafica identica (a meno che non si tratti di un omocodia gestita tramite forcingCode)
	 	- aggiunti controlli di atipicità sugli atti (a meno che non si tratti di una esplicità volontà di registrare atti anomali, gestita tramite forcingCode)
	
    Decodifica
		- Aggiunta tabella decodifica ANSC_95 Tipo Impedimento Generico Unione Civile
		- 9_dec_tipo_allegato : aggiunti allegati con id 91 e 92

    Servizi Cooperativi
        - R009_validazione.yaml
            - Gestione parametro forcingCode (sia response che request) per forzare validazione evento
        - R002_certificazione.yaml
			- Aggiunto campo enteRichiedente per richiesta certificazione (/certificato/{version})
			- Aggiunto campo validoEstero per richiesta certificazione valida per estero (/certificato/{version})
		- R012_firma_dichiarante_elettronica.yaml
			- Aggiunte indicazioni sul valore degli stati per il campo idState (stato della presa visione)

	Web Application
		- sezione firma USC: aggiunto OTP [In ambiente di preproduzione è possibile usare un valore qualsiasi, es '20220730', in produzione sarà necessario inserire l'otp restituito generato dalla propria firma remota : app mobile o token fisico.]
		
	Mapping Casi d'uso
		- Aggiunta condizione obbligatorietà per il mapping caso d'uso, sia per le sezioni che per gli allegati (https://github.com/italia/ansc/issues/75)
            
            
### Removed
	Decodifica
		-78 Accertamento Nascita: Rimosso valore con id 4


## [Versione 1.10.2 - 03-08-2023]

### Fixed
    Servizi Cooperativi 
        - OpenAPI - aggiunta decodifica per genitoreConCittadinanza(https://github.com/italia/ansc/issues/259)
        - OpenAPI - corretto refuso ModelDatiAnnotazione (https://github.com/italia/ansc/issues/276)
        - OpenAPI - aggiunta decodifica consolati per idAnagraficaConsolato (https://github.com/italia/ansc/issues/256)
        
	Decodifica
		- Aggiunta tabella decodifica ANSC_97 per gestione consolati Tipo notifica predisposizione anagrafica (https://github.com/italia/ansc/issues/256)


## [Versione 1.10.1 - 19-07-2023]

### Fixed
    Servizi Cooperativi 
        - OpenAPI - refuso dataNascita ModelSoggetto (https://github.com/italia/ansc/issues/250)
        - OpenAPI - refuso ModelDatiAnnotazione (https://github.com/italia/ansc/issues/249)
        - [R006] fix stato upload firma dichiarante (https://github.com/italia/ansc/issues/253)
    Changelog 1.10.0
		 - Refuso id tabella, quello corretto è ANSC_95 (https://github.com/italia/ansc/issues/251)


## [Versione 1.10.0 - 18-07-2023]

### Added     
    Processo  
        - Emissione certificati semplici con menzione di paternità/maternità
        - Dati secretati: adozioni - Aggiunta la possibilità di modificare il nome     
    Web Application  
        - Emissione certificati semplici con menzione di paternità/maternità
        - Dati secretati: adozioni - Aggiunta la possibilità di modificare il nome   
    Servizi Cooperativi  
        - Gestione path param 'version' servizi rest. Dove il parametro 'version' sarà 
        la major versione di ansc, che in questo momento vale 1, per esempio https://anscservicepre.anpr.interno.it/services/service/doc/allegato/upload/1 
        [Avviso rilascio 1.9.0](https://github.com/italia/ansc/issues/151)
        - Emissione certificati semplici con menzione di paternità/maternità
        - Dati secretati: adozioni - Aggiunta la possibilità di modificare il nome  
	model_evento.yaml 
		- Aggiunto al  ModelUnioneCivile: Impedimento Generico
			 impedimentoGenerico:
			  type: string
			  description: Tipo di impedimento (decodifica ANSC_95)
			  example: "0"
			  
			 soggettoImpedimentoGenerico: # Eventuale ente e motivo di impedimento 
			  $ref: '#/components/schemas/ModelImpedimento'
		- Aggiunti campi oraDecorrenza, minutoDecorrenza, motivoRecupero, descrizioneMotivoRecupero.
	    - Aggiunto idVersion per indicare la versione utilizzata per la creazione dell'evento
		- Aggiunti  campi nuovi al ModelEnteEstero:
			properies:
				idAnagraficaConsolato:
             	 type: string
             	nomeAnagraficaConsolato:
             	 type: string
		- Aggiunto un campo nuovo al ModelTrascrizioneCittadinanza: 
			properties:
				genitoreConCittadinanza  per ricevere il valore della select con i genitori che ha la cittadinanza.
        - Aggiunto il ModelAssistenzaMinori: dati degli assistenti dei minori
		ModelAssistenzaMinori:
		  properties:
			 tipoAssistente :
			  type: string
			  description: Tipo assistenza minori (decodifica ANSC_51) 
			  example: "0"         
			 assistente :
			  description: lista soggetti (al più due soggetti in caso in cui gli assistenti sono entrambi i genitori)(0=Padre. 1=Madre)
			  type: array
			  items:
				$ref: '#/components/schemas/ModelSoggetto'
			 procura: # Provvedimento di nomina del tutore/procuratore speciale
			  $ref: '#/components/schemas/ModelEnteDichiarante'    
	
	Decodifica
		- Aggiunta tabella decodifica ANSC_93 Tipo notifica predisposizione anagrafica
		- Aggiunta tabella decodifica ANSC_95 Tipo Impedimento Generico Unione Civile
		- Aggiunta tabella decodifica ANSC_96 Motivo Recupero

		
### Changed
      
	  Servizi Cooperativi 
      - R012_firma_dichiarante_elettronica.yaml, 
        Aggiunto il campo idEvento al servizio /firmadichiarante/pooling-statoatto/{version}
        Servizio esposto per il pooling di controllo sulla presa visione del 
        dichiarante nel processo di firma. 
        Passando l’idEvento, il servizio risponde con lo stato dell’evento. 
        Passando l’idPresaVisione, il servizio risponde con lo stato della presa visione. 
        Nel caso un cui il servizio sia chiamato con la coppia idEvento/idPresaVisione, 
        risponse con lo stato della presa visione (https://github.com/italia/ansc/issues/134) (https://github.com/italia/ansc/issues/137)
	  
	  - model_evento.yaml  
        - Modifica al  ModelRegimePatrimoniale: il campo assistenzaMinori 
	    assistenzaMinori:
           description: lista contenente i dati degli assistenti dei minori (0=Sposo,1=Sposa)
           type: array
           items:
             $ref: '#/components/schemas/ModelAssistenzaMinori'
	  
	  Decodifica
		- Modifica Valori tabella decodifica ANSC_51 Assistenza Minori
### Removed 
	
    model_evento.yaml  
        - Eliminazione campi al  ModelRegimePatrimoniale:
			presenzaMinori:
			assistenteLegale:
			nominaAssistenteLegale:
		
		- Eliminazione campi al  ModelUnioneCivile:
			difettoEta:
			 impedimentoParentela:

### Fixed
    Servizi Cooperativi 
        - R009 Validazione - Nascita: msg. "La sezione null non dovrebbe essere valorizzata per il caso uso" (https://github.com/italia/ansc/issues/214)
        - R009 Validazione - Indirizzo richiedente su Trascr_006 (https://github.com/italia/ansc/issues/213)
        - R003 Comunicazione - Assenza comunicazioni per eventi morte
        - Dati secretati: adozioni aggiunta la modifica nome
        - R009 Validazione - Matrimoni: sposi minorenni (https://github.com/italia/ansc/issues/164)
        - R009 Validazione - Caso d'uso 52143 Atti di Cittadinanza (https://github.com/italia/ansc/issues/118)
        - R009 Validazione - Validazione usecase 2104 - Morte_004 - 500 Internal Server Error (https://github.com/italia/ansc/issues/191)
        - R009 Validazione - Validazione UseCase Matr_999_2 (https://github.com/italia/ansc/issues/189)
        - R009 Validazione - NullPointer su Annotazione Rettifica (https://github.com/italia/ansc/issues/173)
        - R009 Validazione - ORA-02291: restrizione di integrità violata (https://github.com/italia/ansc/issues/175)
        - R009 Validazione - Caso 1323 - Trascrizione della sentenza straniera di dichiarazione giudiziale di paternità o maternità su richiesta dell’autorità diplomatica o consolare (https://github.com/italia/ansc/issues/70)
        - R009 Validazione - Caso d'uso 432000 - Trascrizione Unione Civile dall'estero - Richiesta di trascrizione da parte del Consolato/Ambasciata (https://github.com/italia/ansc/issues/62)
        - R009 Validazione - Trascr unione civile da consolato: gestione consolati errata (https://github.com/italia/ansc/issues/62)
        - R012 Firma Dichiarante - Richiesta stato firma per Presa Visione (https://github.com/italia/ansc/issues/137)
        - R010 Anteprima - Nascita caso uso servizio - Errore "Dati in ingresso non corretti" (https://github.com/italia/ansc/issues/169)
        - OpenAPI - format date in ModelAttoCollegato -> dataAtto (https://github.com/italia/ansc/issues/205)
        - OpenAPI - Errore Generazione Client con Swagger (https://github.com/italia/ansc/issues/192)
    
    Web Application
        - [311111] Matrimonio con rito civile nella casa comunale: errata interpretazione della formula 62
        - Conferma o mancata conferma di accordo di separazione o divorzio
        - Casi d'uso configurazione: manca il sesso dei soggetti collegati

    Mapping
        - Errore nel file docs/Mapping_casi_uso/3_dec_use_case.csv (https://github.com/italia/ansc/issues/206)


## [Versione 1.9.1 - 19-06-2023]

### Added 
	Servizi cooperativi
		- model_evento.yaml,R001,R003,R005,R006,R008,R009,R014:  Controllo di uniformita e adeguamento formato campi data (https://github.com/italia/ansc/issues/142)
	
	Web Application
		- A005,A006,A008,A010,A013,A016: Controllo di uniformita e adeguamento formato campi data (https://github.com/italia/ansc/issues/142)
		
### Changed
	Servizi Cooperativi 
		- R013: Definite obbligatorie le properties: evento, eventoModificato
		- R001: corretta difformita' di comportamento tra web app e servizio di upload allegato
		- R009: corretto Internal Server Error (500) in risposta all'invocazione del servizio (https://github.com/italia/ansc/issues/168)
		- R008: corretto servizio di ricerca notifiche NullPointerException (https://github.com/italia/ansc/issues/158)
		- R012: corretto errore consultazione stato firma atto evento (https://github.com/italia/ansc/issues/143)
		- R003: corretta intestatzione delle comunicazioni generate da sistema come richiesto da ANUSCA
		- R002: corretti estratti integrali di matrimonio (modificata etichetta officiante) come richiesto da ANUSCA
		- R009: corretto use case MATR_001 per omissioni pubblicazioni (https://github.com/italia/ansc/issues/106)
		- R010: corretta anteprima per usecase 12323100 per datiEventoRiconoscimento.preMorto (https://github.com/italia/ansc/issues/171)
		- R006: corretta firma dichiarante per caso d'uso di servizio 11999999 (https://github.com/italia/ansc/issues/108)
		- R005: corretta consultazione soggetto (https://github.com/italia/ansc/issues/36)
		- R002: corretto errore nella gestione del valore per l'attributo tipoFile (https://github.com/italia/ansc/issues/152)
		- R010: corretta anteprima SAX Error (https://github.com/italia/ansc/issues/117) (https://github.com/italia/ansc/issues/131)
	
	Web Application
		- Corretta regressione sulla funzionalit� 'Modifica e completa' di un atto confermato da servizio cooperativo (https://github.com/italia/ansc/issues/166)
		
		
	Decodifiche
		- 9_dec_tipo_allegato : 998 modificata descrizione (https://github.com/italia/ansc/issues/167)
		- 10_dec_tipo_file: aggiunto formato file di tipo 7PM e Jpeg ed eliminato Doc


## [Versione 1.9.0 - 31-05-2023]

### Added 
	Processo
		- Gestione Parto Gemellare e Plurigemellare
		- Recupero atto firmato dal dichiarante entro un tempo prestabilito (2 ore)
		
	model_evento.yaml
		- Aggiunto idContenitore per legare tra di loro gli atti dei gemelli
	
	Web Application
		- Gestione Parto Gemellare e Plurigemellare
		
	Servizi Cooperativi
        - Gestione Parto Gemellare e Plurigemellare
        
        - R001_allegato.yaml
            - Aggiunto descrizione per upload allegato (/allegato/upload/{version})

### Changed
      Servizi Cooperativi 
		R009_validazione.yaml
			- Aggiunto nuovo servizio per la prenotazione degli id nazionali per il parto gemellare e plurigemellare (/prenota/evento/{version})	
		R007_firma_USC
			- Recupero atto firmato dal dichiarante entro un tempo prestabilito (2 ore)		

### Removed
      Servizi Cooperativi
        R006_firma_dichiarante.yaml
            - Rimosso protocollo per upload firma dichiarante (/firmadichiarante/upload/{version})
            
### Fixed

	Decodifiche
		- Aggiornate descrizioni Use Case e verificati UC mancanti (https://github.com/italia/ansc/issues/114) (https://github.com/italia/ansc/issues/85)
		- 66_dec_tipo_trasmissione: aggiunto ACCERTAMENTO (https://github.com/italia/ansc/issues/23)

	Servizi cooperativi
		- R005 corretta consultazione per Soggetto (https://github.com/italia/ansc/issues/123)
		- R010: corretto servizio Firma Presa Visione (https://github.com/italia/ansc/issues/120) (https://github.com/italia/ansc/issues/131) (https://github.com/italia/ansc/issues/117)
		- R001: corretto servizio upload allegato (https://github.com/italia/ansc/issues/86) (https://github.com/italia/ansc/issues/88)
		- R010: corretto servizio anteprima dati obbligatori (https://github.com/italia/ansc/issues/81)
		- R009: Morte_004 sostituito ente estero con ente italiano (https://github.com/italia/ansc/issues/103)
		- R008: corretto servizio di rivcerca notifiche (https://github.com/italia/ansc/issues/119)
		- R010: corretta anteprima caso uso libero 11999999 (https://github.com/italia/ansc/issues/135)(https://github.com/italia/ansc/issues/136)
		- R002: corretto servizio di certificazione, eliminato controllo bloccante su documento riconoscimento richiedente 
		(https://github.com/italia/ansc/issues/122)


## [Versione 1.8.1 - 19-05-2023]

### Fixed  
    Servizi cooperativi   
        - R009 Corretti controlli sui soggetti collegati nei matrimoni (https://github.com/italia/ansc/issues/116)  
        - R010 Corretto servizio di anteprima: errore compilazione template (https://github.com/italia/ansc/issues/113)  
        - R009 Corretto servizio per caratteri non ammessi (https://github.com/italia/ansc/issues/115)
        - R009 Corretti controlli su morte defunto coiugato/unito civilmente (https://github.com/italia/ansc/issues/44)  



## [Versione 1.8.0 - 16-05-2023]

### Added 
    Mapping casi d'uso   
        - Aggiunti 79 casi d'uso (verificare changelog casi d'uso)  
    Processo  
        - Gestione Dati Secretati  
    model_evento.yaml  
        - Aggiunto flagsecretato per indicare se si tratta se l'atto è secretato o meno  
    Web Application  
        - Gestione Dati Secretati  
        - Aggiunta funzionalità "Firma in seguito" che consente di recuperare la firma successivamente   
    Servizi Cooperativi  
        - Gestione Dati Secretati  

### Changed  
    Web Application   
        - Modificato quick link "Rilascia certificato" : Vengono richieste le generalità dell'intestatario al fine dell'emissione dei certificati di interesse  

### Removed  
    model_evento.yaml  
        - Rimosso genere dalla sottosezione del ModelSoggetto (https://github.com/italia/ansc/issues/89)   

### Fixed  
    Servizi cooperativi   
        - R002 Corretto errore invocazione (https://github.com/italia/ansc/issues/95)  
        - R005 Corretta consultazione annotazioni afferenti ad un evento  
        - R005 Corretto servizio consultazione intestatario (https://github.com/italia/ansc/issues/36)  
        - R006 Corretto servizio firma dichiarante (https://github.com/italia/ansc/issues/97)  
        - R009 Corretti controlli su comune nascita e residenza per i soggetti collegati (https://github.com/italia/ansc/issues/80)  
        - R010 Corretto servizio anteprima Matr_001 (https://github.com/italia/ansc/issues/52)  
        - R010 Corretta anteprima contenuto vuoto (https://github.com/italia/ansc/issues/100)   
        - R012 Corretto controllo tipo contenuto (https://github.com/italia/ansc/issues/92)  
    Web Application  
        - Corretta consultazione atti di matrimonio  


## [Versione 1.7.1 - 08-05-2023]

### Fixed

    Servizi cooperativi  
        - R002 Riferimento model soggetto (https://github.com/italia/ansc/issues/93) 
        - R002 Correzione proprietà openapi richiedete e intestatario (https://github.com/italia/ansc/issues/94) 


## [Versione 1.7.0 - 05-05-2023]

### Added 
	
	 Decodifiche
		- aggiunta decodifca ANSC_93 Tipo notifica predisposizione anagrafica
	
    model_evento.yaml  
        - Aggiunti al ModelEnteEstero: il campo comuneEstero  
        - Modificato interamente il ModelDatiAnnotazione, riscritto in questo modo:  
```
			ModelDatiAnnotazione:  
      			description: classe che raccoglie i dati per le annotazioni contestuali  
      				properties:  
			          testoAnnotazione:  
			            type: string  
			            description: Contiene il testo completo dell’annotazione da presentare come annotazione a margine dell’atto  
			            example: "ABCD"     
			          tipoAnnotazione:  
			            type: string  
			            description: tipo di annotazione contestuale registrata  
			            example: "1"   
```

    Servizi Cooperativi  
        - R006_firma_dichiarante.yaml, Aggiunti i seguenti campi al FirmatarioDTO: sesso, dataNascita (resi obbligatori codice fiscale o dati anagrafici)  
        - R014_evento_validita.yaml, Aggiunto servizio cooperativo per Gestione data di validità verso anagrafe ai fini della predisposizione anagrafica  
        - R009, Corretta trascrizione matrimonio dall'estero, aggiunto ente estero (https://github.com/italia/ansc/issues/63)  
        - Aggiunta Gestione Annotazioni Contestuali  
        - Aggiunti ulteriori allegati per il matrimonio  
		  
    Web Application  
        - Aggiunta Gestione data di validità verso anagrafe nel servizio di firma dichiarante  
        - Rimossi madre e padre dai casi d'uso :   
           - [11315200] Dichiarazione nei termini di filiazione fuori dal matrimonio resa all'usc da ostetrica o altro sanitario che ha assistito al parto - nato vivo ma morto prima della dichiarazione  
           - [11315100] Dichiarazione nei termini di filiazione fuori dal matrimonio resa all'usc da ostetrica o altro sanitario che ha assistito al parto - nato morto  
        - Trascr_005 - Corretta minuta dell'atto  
        - Citt_005, Citt_007, Citt_011, Citt_013: aggiunti ulteriori allegati  
        - Gestiti comuni validi alla data  

    Decodifiche  
        - Aggiunta di valori ammissibile per tipo Allegato (ANSC_9)   
        - Aggiornata tabella di decodifica 61 (https://github.com/italia/ansc/issues/79)  

### Changed
      Servizi Cooperativi 
		R002_certificazione.yaml
			- sostituito idAnprRichiedente con richiedente
			- sostituito idAnprRiferimentoAtto con intestatario
			- modificato tipo Idutenterilascio da BigDecimal a String in ModelCertificato
### Removed
      Servizi Cooperativi 
    R002_certificazione.yaml		
    - cancellazione idUsc	


## [Versione 1.6.2 - 20-04-2023]

### Fixed

    Servizi cooperativi  
        - R009 Validazione caso d'uso matrimonio religioso (https://github.com/italia/ansc/issues/61)  
        - R002 Estratti per copia integrale di unione civile e matrimoni: corretta intestazione  


    Decodifica ANSC_26 (26_dec_tipo_comunicazione)  
        - Aggiunta tabella (https://github.com/italia/ansc/issues/66)  

    Web Application  
        - Matr_002, Matr_005: aggiunto l'officiante  
        - Morte_005: corretto luogo morte nel certificato semplice  
        - Trascr_022: corretta tarascrizione resa dalla direzione sanitaria (https://github.com/italia/ansc/issues/64)  
        - UnCiv_001: corretta minuta dell'atto  
        - Matr_004, Matr_001, Matr_007, Matr_005, UnCiv_001: corretto orario di celebrazione dell'evento  
        - Casi d'uso Matrimonio rito religioso: corretta obbligatorietà dei dati e flusso di firma (https://github.com/italia/ansc/issues/61)  


## [Versione 1.6.1 - 17-04-2023]

### Added

    Mapping casi d'uso annotazioni (l'implementazione era già disponibile nella versione 1.6.0, è stata integrata la documentazione di mapping)


## [Versione 1.6.0 - 07-04-2023]

### Fixed

    Servizi cooperativi
		- model_evento.yaml
			-  eliminato formato data per il campo numeroprotocollo.
			(https://github.com/italia/ansc/issues/39)
			- Cancellazione delle proprietà sul model ModelEnteDichiarante:
				- nazioneEnte
				- nomeNazioneEnte
			(https://github.com/italia/ansc/issues/41)

		- R007,R009,R012, base_servizi.yaml
				- Sostituito il type:number con type:integer
				(https://github.com/italia/ansc/issues/43)

		- R005 Consultazione evento - ricerca annotazioni
			  (https://github.com/italia/ansc/issues/20)

		- R009 Validazione caso d'uso dichiarazione con procura
			  (https://github.com/italia/ansc/issues/32)

		- R005 consultazione intestario
			  (https://github.com/italia/ansc/issues/36)

		- R006 firma dichiaranti
			  (https://github.com/italia/ansc/issues/40)

	Decodifica ANSC_3 (3_dec_use_case)
		- Normalizzazione descrizioni casi d'uso ed eliminazione duplicati
		  (https://github.com/italia/ansc/issues/31)

	Web Application
		- Unione civile fuori dalla casa comunale: gestione vicesegretario
		- Matrimoni/Unioni cviile : officiante non presente nelle formule
		- Citt_005, Citt_007, Citt_011, Citt_013: il soggetto intestatario deve essere anche firmatario
		- Eliminato caso Matr_006: matrimonio in pericolo di vita si delega di altro comune
		- Unione civile fuori dalla casa comunale UnCiv_002: aggiunto indirizzo

### Added

    Processo
		- Gestione Annotazioni per Errore Materiale
		- Gestione Annotazioni per Caso d'uso di servizio (comunicazione da altri comuni)
		- Gestione Annotazioni per Caso d'uso di servizio (comunicazioni da altre amministrazioni)

    Web Application
		- Gestione Annotazioni per Errore Materiale
		- Gestione Annotazioni per Caso d'uso di servizio (comunicazione da altri comuni)
		- Gestione Annotazioni per Caso d'uso di servizio (comunicazioni da altre amministrazioni)

    Servizi Cooperativi
		- [R002] Aggiunta proprieta' idEvento a CertificatoRequest
		- [R005] Aggiunta proprieta' idEvento
		- [R009_validazione.yaml] Aggiunta obbligatorieta' campo hashAllegato
		- model_evento.yaml
			- Aggiunta obbligatorieta' campo numeroatto
			- Aggiunto nuovo campo idRiconoscimentoSentenza: Identificativo ricoscimento.
			- Nel ModelAttoCollegato aggiunto campo id
			- Nel ModelUnioneCivile aggiunto campo obbligatorio ruoloSegretario
			- Nel ModelMatrimonio aggiunto campo obbligatorio ruoloSegretario
			- Rimozione delle proprieta' sul model ModelEnteDichiarante:
				- nazioneEnte
				- nomeNazioneEnte
	Decodifica
		- Aggiunta tabella decodifica ANSC_91 Ruolo Segretario
		- Aggiunta tabella decodifica ANSC_92 Difetto di eta' dei coniugi
		- Aggiornata tabella decodifica ANSC_49 regime patrimoniale aggiunte le opzioni "Convenzioni matrimoniali" e "Non specificata"

### Changed

    Servizi Cooperativi
		- [R012_firma_dichiarante_elettronica.yaml]
	   		 Modificata descrizione della property idPresaVisione allo schema FirmaDichiaranteOnlineAnnullaLinkRequest.
		- Eliminato caso Matr_006: matrimonio in pericolo di vita si delega di altro comune
		- [R001_allegato.yaml] impostati tutti i campi di AllegatoInput a required

## [Versione 1.5.3 - 21-03-2023]

### Fixed
	Servizi cooperativi
		- [R091] Fix tabella decodifica ANSC_31 fix restituita da servizio servizio R901
		- [R005] La proprietà 'eventi' dello schema ConsultazioneANSCResponse diventa 'modelEventoDTO' (https://github.com/italia/ansc/issues/29)
		- [R012] Corretto ed esplicitato il flusso di presa visione (https://github.com/italia/ansc/issues/16)
		- [R012] Fix schema openapi (https://github.com/italia/ansc/issues/34)	
		- [R091] Caratteri speciali tabella ANSC_9 (https://github.com/italia/ansc/issues/30)	
		- [openapi] Allineata proprietà ModelSoggetto da datanascita a dataNascita (https://github.com/italia/ansc/issues/37)	

## [Versione 1.5.2 - 17-03-2023]

### Fixed
	Decodifica
		- Aggiornamento tabella decodifica ANSC_31 per la scelta del cognome in fase di dichiarazione di nascita 
		- Estratti e certificati: migliorato il layout condiviso (eliminata parola semplice, eliminata parola certificato 
		- Morte 007: corretto binding duplicato
		- Modificata descrizione dei casi d'uso Casi d'Uso - 12214300 e 12216300
	Servizi cooperativi
		- Trascrizione atto nascita estera: gestione stato estero mancante
		- Tascr_999: corretto malfunzionamento anteprima
		- R005: Corretto il risultato della ricerca del servizio di consultazione che non restituiva i dati dell'intestatario (GitHub issue #21)
		- R009: Corretto luogo di nascita estero per il servizio di validazione
		- R006: Corretta la possibilità di inserire la lista dei firmatari del servizio di firma dichiarante
		- R010: Corretto malfunzionamento anteprima per Tascr_999
		- R012: Aggiunto in FirmaDichiaranteOnlineInvioEmailRequest l'input firmatario, idEvento ed idAnsc e rimosso l'input idPresaVisione
	Web Application
		- Aggiornamento formule aderendo a circolari successive (legge 219) 
		- Accessibilità: fix varie per accessibilità (titoli pagine, migliorata breadcrumb,navigabilità da tastiera ec..) 
		- Accordo di scioglimento matrimonio/Accordo di separazione personale tra coniugi: gestione calendario per date future e revisione dell'aobbligatorietà degli allegati
		- Sezione avvisi: ordinamento avvisi in base alla data di inserimento dell'avviso
		- Dichiarazioni di nascita: impostazione automatica dello stato di nascita Italia
		- Dic_Nasc_076: aggiornamento minuta atto (inserita preposizione mancante 'da')
		- Dic_Nasc_064: aggiornamento minuta atto (eliminato il prericonoscimento del padre e lasciato solo quello della madre)
		- Matr_008 e in tutti i casi del matrimonio: inserite formule 62 e 62-bis nella minuta dell'atto per la scelta del regime patrimoniale
		- Citt_043: corretta la minuta dell'atto e i dati richiesti
		- Matr_Riconc_001: aggiornamento obbligatorietà allegati; nei certificati, resi disponibili solo gli estratti
		- Trascrizione della convenzione di negoziazione assistita ai sensi dell'art.6: reso unico l'accordo tra i coniugi
		- Trascrizione atto nascita estera: corretta obbligatorietà di stato comune e provincia
		- Caso uso 51104: è stato aggiunto idRiconoscimentoSentenza al modelEvento e al mapping del caso d'uso
		- Dic_021 e Dic_022: eliminata la frase CON CITTADINANZA ITALIANA dalla minta dell'atto
		- Morte_006: eliminato il richiamo all'art.19 dalla minuta dell'atto
		- Trascr_Matr_002: aggiunto art. 63 alla minuta dell'atto e abilitati gli estratti e i certificati	
### Added
	Aggiunto un nuovo campo al model ModelEvento:
		- idRiconoscimentoSentenza:type: stringdescription: Identificativo ricoscimento. 
	Aggiunto due nuovi campi al model ModelEnteDichiarante:
		- nazioneEnte
		- nomeNazioneEnte

## [Versione 1.5.1 - 2023-03-07]
### Added	
	Decodifica
		- Aggiunta decodifica ANSC_28 - tipo firma (https://github.com/italia/ansc/issues/9)

## [Versione 1.5.0 - 2023-03-03]
### Added	
	Decodifica
		- Aggiunta decodifica ANSC_79 - tipo rettifica
	Processo e Web Application
		- Gestione delle Annotazioni di Rettifica		
		- Gestione dei certificati nel caso di rettifica
	model_evento.yaml
		- Aggiunto modello ModelScioglimentoUnioneCivile Data ricezione comunicazione scioglimento unilaterale dell'unione civile
		- Nel ModelScioglimentoUnioneCivile aggiunta nuova proprietà dataRicezione		
	R013_rettifica_validazione.yaml
	   - Aggiunto il servizio per la validazione delle annotazione di rettifica per il servizio cooperativo
	R901_config_decodifica.yaml
		- Aggiunto servizio di accesso alle tabelle di decodifica
	R901_config_decodifica.yaml
		- Aggiunto servizio di accesso alle tabelle di decodifica	
	Guida operativa
		- Aggiunto sguida operativa docs/Guida_operativa_ANSC.pdf			
### Changed
	Piani di test
		- Aggiornato piano di test docs/CasiTest/ANSC_Piano_Test.xlsx	
	Nota processo annotazione e servizi cooperativi ( e relativi payload )
		-  Note/NotaProcessoAnnotazioniAndQuickCoopServiceFlow/NotaProcessoAnnotazioniAndQuickCoopServiceFlow.pdf

## [Versione 1.4.1 - 2023-02-02]
### Added
	Piani di test
         - Aggiunto piano di test docs/CasiTest/ANSC_Piano_Test_R03.xlsx

## [Versione 1.4.0 - 2023-02-14]
### Added
	model_evento.yaml
		- Aggiunto modello ModelRettifica che contiene i dati pertinenti alla rettifica di un evento e in particolare:
			- eventoCollegato che rappresenta l'evento da rettificare
			- dettaglioRettifica che contiene il testo libero da inserire nella formula
		- Aggiunto modello ModelDatiLingua per l'invio della composizione completa in altre lingue, da tenere presente che 
			- E' stata inclusa solo l'interfaccia OpenAPI, l'implementazione seguirà in un prossimo rilascio.
	Decodifica
		- Aggiunta decodifica ANSC_78 - accertamento nascita
	Annotazione automatiche
		- Generazione annotazioni automatiche in seguito a eventi successivi alla nascita 
	R007_firma_usc.yaml
		- Aggiunto parametro modalità di firma usc (idModalitaInput), e inseriti parametri di esempio per invocazione		
	R005_consultazione_ansc.yaml
		- Aggiunta operazione di ricerca intestatari
	R009_validazione.yaml
		- Aggiunta operazione per collegamento di una annotazione a un evento esistente
	R010_anteprima.yaml
		- La request del servizio /anteprima/evento/{version} ha un parametro non obbligatorio in più per richiedere l'anteprima senza watermark
		
## [Versione 1.3.2 - 23-01-02]
### Added
	Regole
		- Obbligatorietà degli atti di nascita degli sposi nel matrimonio condizionata allo stato di nascita del soggetto #118293
		- Obbligatorietà dei dati sull'autorizzazione per difetto d'età nel matrimonio condizionata al tipo di difetto d'età. In particolare se vale 0, ossia nessun difetto d'età, non viene imposta. #118293
		- Obbligatorietà dei dati dell'assistente legale nel matrimonio condizionata alla presenza minori. In particolare se vale 0, ossia senza presenza minori, non viene imposta. #118293
			- idTipoRettifica che può valere 0 = per annullamento dell'evento collegato oppure 1 = per la modifica dell'evento collegato
		- Nel ModelEvento aggiunta nuova proprietà datiRettifica
		- Nel ModelDatiDiNascita aggiunta proprietà tipoAccertamento
		- Aggiunto modello ModelDatiLingua che contiene i dati per la gestione multilingue
		- Nel ModelEvento aggiunta nuova proprietà datiLingua
	model_evento.yaml
		- Aggiunto ModelImpedimento
		- Nel ModelImpedimento aggiunte la proprietà certificato
		- Nel ModelImpedimento aggiunte la proprietà motivazione
		- Nel ModelMatrimonio aggiunte la proprietà soggettoImpedimento
		- Nel ModelMatrimonio aggiunte la proprietà impedimentoSposo
		- Nel ModelMatrimonio aggiunte la proprietà impedimentoSposa
		- Nel ModelUnioneCivile aggiunta la proprietà soggettoImpedimentoCivile
		- Nel ModelUnioneCivile aggiunta la proprietà impedimentoSposo
		- Nel ModelUnioneCivile aggiunta la proprietà impedimentoSposa
	
## [Versione 1.3.1 - 2022-12-27]
### Added
	model_evento.yaml
		- Nel ModelScioglimentoUnioneCivile aggiunta proprietà autoritaGiudiziaria
		
	Processo
		- Generazione notifiche verso comuni interessati all'evento firmato
		- Generazione comunicazione verso enti terzi dopo la firma dell'evento
		
	Web Application
		- Sezione notifiche: consultazione e ricerca
		- Sezione comunicazioni: download comunicazioni verso enti terzi

## [Versione 1.3.0 - 2022-12-20]
### Added
    Web Application
		- Casi d'uso di servizio: casi d'uso liberi per tipologia di evento, per tutti i registri
		- Registrazione casi d'uso relativi al perimetro censito nel piano di test (versione 1 e versione 2) 
		
	model_evento.yaml
		- Nel ModelDatiEventoCittadinanza aggiunta la proprietà tipoEventoCittadinanza
		- Nel ModelMatrimonio aggiunte le proprietà impedimentoSposo e impedimentoSposa
		- Aggiunto il modello ModelImpedimento

## [Versione 1.2.0 - 2022-11-30]
### Added
    Web Application
		- Registrazione eventi
		- Consultazione eventi
		- Recupero eventi in bozza
		- Emissione certificati
		- Firma digitale dichiarante
		- Firma analogica dichiarante
		- Firma remota Ufficiale di stato civile
		- Anteprima evento
		- Consultazione avvisi di sistema
		
	model_evento.yaml
		- Nel ModelEvento inserito il ruolo dell'ufficiale di stato civile nelle dichiarazioni
		- Nel ModelSoggetto inserito idstatocivile
		- Nel ModelConsenso aggiunto l'atto di consenso
		- Aggiunto ModelAnnotazione
		- Nel ModelEvento nuova proprietà datiAnnotazione
		- Nel ModelEvento nuova proprietà datiEventoMorte
		- Aggiunto ModelAssenso
		- Nel ModelEvento nuova proprietà datiAssenso
		- Nel ModelAttoCollegato nuova proprietà redattoNellaCasaComunale
		- Nel ModelAttoCollegato nuova proprietà luogoRedazione
		- Nel ModelAttoCollegato nuova proprietà oraAtto
		- Nel ModelAttoCollegato nuova proprietà minutoAtto
		- Nel ModelAttoCollegato nuova proprietà operatoreNome
		- Nel ModelAttoCollegato nuova proprietà operatoreCognome
		- Nel ModelAttoCollegato nuova proprietà ruoloOperatore
		- Nel ModelSoggetto nuova proprietà idstatocivile
		- Nel ModelEnteEstero nuova proprietà nomeEnteEstero
		- Nel ModelAllegatoRif nuova proprietà idTipoAllegato
		- Nel ModelDatiDiMorte nuova proprietà dataPresuntaMorteDa
		- Nel ModelDatiDiMorte nuova proprietà dataPresuntaMorteA
		- Nel ModelDatiDiMorte nuova proprietà oraPresuntaMorteDa
		- Nel ModelDatiDiMorte nuova proprietà oraPresuntaMorteA
		- Nel ModelDatiDiMorte nuova proprietà testoDataPresuntaMorte
		- Nel ModelAscendente nuova proprietà dataMorte
		- Nel ModelDatiEventoCittadinanza nuova proprietà altraCittadinanzaRiacquistata
		- Nel ModelDatiEventoCittadinanza nuova proprietà idMotivoPerditaCittadinanza
		- Nel ModelDatiEventoCittadinanza nuova proprietà dataAssunzione
		- Nel ModelDatiEventoCittadinanza nuova proprietà datoreEstero
		- Nel ModelDatiEventoCittadinanza nuova proprietà nomeDatoreLavoro
		- Nel ModelMatrimonio nuova proprietà descrizioneRitoReligioso
		- Nel ModelMatrimonio nuova proprietà ritoRiconosciuto
		- Nel ModelPubblicazione nuova proprietà idProvincia
		- Nel ModelPubblicazione nuova proprietà idComune
		- Nel ModelTrascrizioneCittadinanza nuova proprietà ulterioreCittadinanza
		- Nel ModelTrascrizioneCittadinanza nuova proprietà descrizioneUlterioreCittadinanza
		- Nel ModelTrascrizioneNascita nuova proprietà idTipoRichiedente
		- Nel ModelTrascrizioneNascita nuova proprietà descrizioneTipoRichiedente
		- Nel ModelEnteDichiarante nuova proprietà descrizione
		- Nel ModelTrascrizioneNascita nuova proprietà tipoRiconoscimento
		- Nel ModelTrascrizioneNascita nuova proprietà figlioDiIgnoti
		- Nel ModelTrascrizioneNascita nuova proprietà riconoscimentoPaternoConSentenza
		- Nel ModelDatiEventoMorte nuova prorpietà dataTrasmissione
		- Nel ModelTrascrizione nuova proprietà atto
		- Nel ModelDatiEventoRiconoscimento nuova proprietà tipoSceltaCognome
		- Nel ModelDatiEventoRiconoscimento nuova proprietà nuovoCognome
		- Nel ModelTrascrizioneNascita nuova proprietà specificaLuogoNascita
		- Nel ModelTrascrizioneNascita nuova proprietà nuovoNome
		- Nel ModelTrascrizioneNascita nuova proprietà cognomeAggiunto
		- Nel ModelTrascrizioneNascita nuova proprietà nomeAggiunto
		- Nel ModelDatiEventoRiconoscimento nuova proprietà assensoAtto
		- Nel ModelEvento nuova proprietà attoNotarileConsensoMadre
		- Nel ModelEvento nuova proprietà attoNotarileConsensoPadre
		- Nel ModelMatrimonio nuova proprietà attoNascitaSposo
		- Nel ModelMatrimonio nuova proprietà attoNascitaSposa
		- Nel ModelUnioneCivile nuova proprietà attoNascitaConiuge1
		- Nel ModelUnioneCivile nuova proprietà attoNascitaConiuge2
		- Nel ModelScioglimentoUnioneCivile nuova proprietà dataConfermaAccordo
		- Nel ModelScioglimentoUnioneCivile nuova proprietà presenzaConiuge1
		- Nel ModelNegoziazioneAssistita nuova proprietà testoTrascrizione
		- Nel ModelNegoziazioneAssistita nuova proprietà accordo
		- Creato ModelCertificatoUnioneCivile
		- Nel ModelUnioneCivile nuova proprietà certificatoCostituzione1
		- Nel ModelUnioneCivile nuova proprietà certificatoCostituzione2
		
### Deprecated
		- Nel ModelDatiEventoRiconoscimento il campo assensoReso è deprecato usare al suo posto il nuovo assensoAtto
		
### Changed
	model_evento.yaml
		- Nel ModelAttoCollegato il campo IdANSC è stato rinominato IdAnsc
		- Nel ModelAttoCollegato il campo numeroAtto è stato rinominato numeroatto
		- Nel ModelAttoCollegato il campo dataFormazione è stato rinominato dataformazione
		- Nel ModelConsenso il tipo di datiProdotti da boolean a String
		- Nel ModelDatiEventoRiconoscimento il tipo di datiProdotti da boolean a String
		- Nel ModelMatrimonio corretto errore di battitura offciante è diventanto officiante
		- Nel ModelUnioneCivile corretto errore di battitura offciante è diventanto officiante
		
### Removed
	model_evento.yaml
		- Nel ModelConsenso rimosso comuneRiconoscimento
		- Nel ModelConsenso rimosso riconoscimento
		- Nel ModelAttoEstero non servono i dati di data, descrizione ed estremi che sono presi dal ModelEnteEstero
		- Nel ModelEnteRichiedente tolti giorno, mese e anno trascrizione perché ridondanti
		- Nel ModelUnioneCivile rimossi i dati che riguardano i dati del certificato di costituzione dell'unione civile perché inseriti in un model apposito
		
## [1.1.4]
### Added
	model_evento.yaml
		- Nel ModelPubblicazione aggiunto idComune per l'id del comune
		- Nel ModelPubblicazione aggiunto idProvincia per l'id della provincia
### Changed
	model_evento.yaml
		- Nel ModelPubblicazione il comune indica il nome del comune
		- Nel ModelPubblicazione la provincia indica la sigla della provincia
### Fixed
	model_evento.yaml
		- Nel ModelMatrimonio corretto errore digitazione offciante è diventato officiante
		- Nel ModelUnioneCivile corretto errore digitazuibe offciante è diventato officiante
		
## [Versione 1.1.3 - 2022-09-27]
### Added
	model_evento.yaml
		- Nel ModelSoggetto inserito un flag che indica se il soggetto è il dichiarante
		- Nel ModelSoggetto inserito un flag che indica se il soggetto è il comparente
		- Nel ModelSoggetto inserito un flag che indica se il soggetto è un firmatario
		- Nel ModelAttoCollegato: inserita dataFormazione
		- Nell'Evento principale: aggiunto array datiRiconoscimentoFigli per i riconoscimenti multipli nel matrimonio
		- Introdotti campi ID per comuni, province, stati e nazionalità/cittadinanze, in particolare:
			- ModelEvento.idComuneRegistrazione
			- ModelEvento.idProvinciaRegistrazione
			- ModelAttoCollegato.idComuneRegistrazione
			- ModelAttoCollegato.idProvinciaRegistrazione
			- ModelSoggetto.idComuneNascita
			- ModelSoggetto.idProvinciaNascita
			- ModelSoggetto.idStatoNascita
			- ModelSoggetto.idComuneResidenza
			- ModelSoggetto.idProvinciaResidenza
			- ModelSoggetto.idStatoResidenza
			- ModelSoggetto.idNazionalita
			- ModelEnteDichiarante.idComuneEnte
			- ModelEnteDichiarante.idProvinciaEnte
			- ModelDatiDiMorte.idComuneMorte
			- ModelDatiDiMorte.idProvinciaMorte
			- ModelDatiDiMorte.idStatoMorte
			- ModelDatiEventoCittadinanza.idProvinciaResidenza
			- ModelDatiEventoCittadinanza.idComuneResidenza
			- ModelDatiEventoCittadinanza.idUlterioreCittadinanza
			- ModelLuogo.idComune
			- ModelLuogo.idProvincia
			- ModelLuogo.idStato
			- ModelMatrimonio.idProvinciaComuneDelegante
			- ModelUnioneCivile.idProvinciaCertificatoCostituzione
			- ModelUnioneCivile.idProvinciaComuneDelegante

	Implementazione microservizi:
		- Microservizio di firma digitale dichiarante: Annullamento del link inviato al dichiarante
		- Microservizio di firma digitale dichiarante: Pooling Stato Atto
		- Microservizio di firma digitale dichiarante: Conferma Presa Visione
		- Microservizio di firma digitale dichiarante: Anteprima Atto
### Changed
	decodifiche.md
		- Rivisto elenco dichiaranti
	model_evento.yaml 
		- L'id ANSC è stato rinominato da idansc a idAnsc
		- Modifica esempio tipoDichiarante che sarà un id numerico
		- Il campo datiRiconoscimento è deprecato, usare datiProdotti
		- La decodifica del tipoImpedimento nel ModelSoggetto è ANSC-32

	Implementazione microservizi:
		- task checkfile: Code Review dei punti di eccezione
		- task checkfile: Aggiunti i valori di Descsoggettointestatario e Nomecomuneform nella creazione della notifica
		- task checkfile: Aggiornato task predisposizioni con l'allineamento delle tabelle
		- Microservizio di Comunicazioni: Code Review dei punti di eccezione
		- Microservizio di firma USC: Code Review dei punti di eccezione
		- Microservizio firma digitale dichiarante: Code Review dei punti di eccezione
		
### Fixed
	R012_firma_dichiarante_digitale.yaml
		- Modificato path errato
	Implementazione microservizi
		- task checkfile: Comune di competenza nella creazione della Notifica
		- Microservizio di Comunicazioni: Fix UTF-8
		- Microservizio di firma USC: Fix UTF-8
		- Microservizio firma digitale dichiarante: Fix UTF-8
						
## Versione 1.0.2 - 2022-09-05
### Added
	model_evento.yaml 
		- Inserito tipoScomparsa nelle trascrizioni di morte
		- Nel ModelDatiDichiarante aggiunto il campo dichiarazioneCongiunta
		- Aggiunta le liste di Id ANSC per i parti gemellari
		- Flag che indica se l'atto è stato redatto nella casa comunale
	R002_certificazione.yaml 
		- Aggiunti i seguenti campi al CertificatoRequest: IdAnsc, idAnprRichiedente, idAnprRiferimentoAtto, idUsc, idTipoCertificato, e i seguenti campi al CertificatoResponse: contenuto, nomeFile, tipoFile, tipoContenutoFile, idCertificato, codice, descrizione, tipologia 
	R012_firma_dichiarante_digitale.yaml
		- Nuovo servizio di firma digitale
	Implementazione microservizi
		- Nuovo microservizio di firma remota dichiarante
	
### Changed
	model_evento.yaml 
		- Aggiunti i riferimenti alle decodifiche dove mancanti nei commenti dei campi
		- Accorpati i dati della data di nascita in un unico campo
		- I dati di nascita, di morte, di rinvenimento e quelli specifici del dichiarante sono stati scorporati da quelli del soggetto e messi direttamente nell'evento
		- I dati di nascita sono stati riorganizzati togliendo le ridondanze rispetto al ModelEvento e inserendo la sceltaCognome
		- Riordinati i dati del ModelEvento
		- ModelSoggetto.datanascita -> ModelSoggetto.dataNascita
	Implementazione microservizi
		- In tutti i microservizi è stata implementata la verifica di sicurezza
		- In tutti i microservizi è stato implementato il meccanismo di tracciamento
		- Microservizio di firma remota: implementata verifica stato dell'evento prima della firma
		- Microservizio di validazione: implementata verifica dell'id anpr passato
### Removed
	R002_certificazione.yaml 
		- CertificatoRequest.DatiRicerca, CertificatoResponse.ModelCertificato
	model_evento.yaml 
		- Tolti campi inutili registro, parte, serie dal ModelEvento
### Fixed
	model_evento.yaml 
		- Rimozione carattere < nella descrizione di un elemento
		- Typo nella descrizione del numero atto
		- Corretto errore nella definizione del luogo di redazione dell'evento
		- Tolti riferimenti errati nei commenti del ModelLuogo all'evento di decesso
	R005_consultazione_ansc.yaml 
		- Eliminato campo idAnsc nella consultazione per soggetto

## Versione 1.0.0 - 2022-07-18
### Added
	model_evento.yaml 
		- Allineati i dati secondo quanto emerso dall'analisi dei nuovi casi di Cittadinanza
### Fixed
	R005_consultazione_ansc.yaml 
		- Refactor del campo idANSC
	model_evento.yaml 
		- Refactor del campo idANSC
