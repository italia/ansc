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

## [Versione 1.5.2 - 2023-02-28]
### Added	
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
