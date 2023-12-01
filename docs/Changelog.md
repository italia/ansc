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

## [Unreleased]

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
