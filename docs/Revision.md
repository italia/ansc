# Revision - retrocompatibilità servizi cooperativi

Il meccanismo delle revision viene introdotto con la patch 1.27.6 
e si aggiunge ai due meccanismi di retrocompatibilità già presenti in ANSC : 

* supporto [major version](https://github.com/italia/ansc/blob/main/ChangeManagement.md) (corrispondente al primo numero della versione di ANSC, al momento non è mai stato usato)
* [idVersion](https://github.com/italia/ansc/blob/main/docs/Decodifiche/100_dec_versione.csv) data model (usato per il solo versionamento del data model)

Questo meccanismo è dedicato ai soli servizi cooperativi, in quanto la web app aderisce
sempre all'ultima revision disponibile.

In sostanza, quando viene modificato un comportamento di uno o più path dei servizi cooperativi
in modo che potrebbe risulta non del tutto retrocompatibile per i client, il sistema ANSC potrebbe
decidere di mantenere il supporto a entrambi i comportamenti.

In questo caso sarà chi desidera il nuovo comportamento a doverlo richiedere espressamente,
le nuove revision vanno attivati con il query param `revision`, ad esempio : 

`https://anscservice.anpr.interno.it/services/service/ricerca/consultazione/ansc/intestatario/1?revision={revisionId}`

Ecco l'elenco delle revision attualmente attive : 

| revision id | introduzione | descrizione                                                                                                                                   |
|-----------|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| 2000001   | -            | comportamento di default, equivalente a non indicare affatto il parametro `revision`                                                          |
| 2000002   | 2024-04-18   | `R005` adegua l'output del path `/consultazione/ansc/intestatario` a quanto dichiarato nell'openapi <https://github.com/italia/ansc/issues/827> |
| 2000003   | 2024-04-18   | `R008` adegua l'output del path `/notifiche/getNotificheByEvento` a quanto dichiarato nell'openapi <https://github.com/italia/ansc/issues/830>  |

NOTA: ogni revision successiva attiva anche le precedenti. se, ad esempio, 
si passa al path `/consultazione/ansc/intestatario` la revision `2000003`
si attiverà comunque il comportamento della revision `2000002`.