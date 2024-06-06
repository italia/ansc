# Quickstart Multilingua

[index](index.md)

Questo documento è un semplice quickstart per l'uso delle funzionalità multilingua.

## Applicabilità

- Le funzionalità di multilinguismo si applicano solo ai comuni per i quali è espressamente abilitata una lingua addizionale.
- Tali comuni sono gli stessi configurati per il sistema [ANPR](https://www.anagrafenazionale.interno.it/area-tecnica/documentazione-tecnica/).
- Dall'analisi con gli stake holder è stato evidenziato che, se un comune è abilitato all'uso di lingue addizionali, è obbligatorio formare l'atto anche in tali lingue. (*)

(*) Tale obbligo è esteso a tutte le versioni attualmente valide del software, in quanto nessun comune multilingua 
è ancora in produzione, quindi non c'è nessun blocco alla formazione di atti reali.

### Codici lingue

I codici lingua utilizzabili sono gli stessi della tabella 14 di ANPR reperibili sul portale <https://www.anagrafenazionale.interno.it/area-tecnica/tabelle-di-decodifica/>

Quelli effettivamente attivi e utilizzabili con un comune al momento sono . 

| codice | lingua  |
|--------|---------|
| `DE`   | Tedesca |

## [R009] - Servizio di validazione

Per il servizio di validazione, i comuni multilingua devono fornire sempre la sezione  `datiLingua` descritto nello [Schema OpenAPI ModelDatiLingua](https://github.com/italia/ansc/blob/v1.29.0/docs/openapi/model_evento.yaml#L2983) :

```yaml
ModelDatiLingua:
  description: I dati della composizione in una lingua addizionale
  properties:
    codiceLingua:
      type: string
      description: Il codice della lingua aggiuntiva
      example: 'DE'
    composizioneCompleta:
      type: string
      description: La composizione completa nuova nuova lingua
      example: "L'anno 2020 add 8 del mese di 1 alle ore 12 e minuti 1 nel(1) la Casa Comunale avanti a me CESENA ANSC Ufficiale dello Stato Civile del Comune di CESENA (2) Per delega avuta\ne' comparsa cognomeMadre nomeMadre nata in ROMA l 1977-11-12 (3) residente in ROCCA CANTERANO\n"
    [..]
```

La sezione `datiLingua` e le proprietà `codiceLingua` / `composizioneCompleta` sono sempre obbligatorie per le lingue addizionali.

```json
{
    "code": "400003",
    "severity": "E",
    "text": "Le informazioni in lingua non sono valorizzate"
}
```

Altre proprietà sono obbligatorie se necessarie per le formule. L'applicazione guiderà con messaggi specifici per le proprietà mancanti,
In modo simile a come già avviene per le obbligatorietà del mapping :

```json
{
    "code": "400003",
    "severity": "E",
    "text": "In Lingua la proprieta ${nomeProprieta} non e valorizzata ma in Italiano si"
}
```

Ecco un esempio completo di [payload della richiesta di validazione](payload/1_validazione.json).

## [R002] - Servizio di certificazione

Nel servizio di certificazione, come specificato nella relativa specifica [OpenAPI](https://github.com/italia/ansc/blob/v1.29.0/docs/openapi/R002_certificazione.yaml#L94) è necessario richiedere le lingue addizionali per le quali si vuole che il certificato venga generato : 

```yaml
codiciLingueCertificato:
  type: array
  items:
   type: string
   description: Codici lingue aggiuntive in cui il certificato verrà prodotto
```

## Altri servizi cooperativi

Per gli altri servizi cooperativi la gestione delle lingue addizionali dovrebbe essere trasparente.