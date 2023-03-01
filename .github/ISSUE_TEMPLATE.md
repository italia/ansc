--- TESTO DA ELIMINARE ---

Nel campo "Title" (qua sopra), usa "[codice flusso] Breve descrizione del problema". Per esempio: "[R001] problema nella verifica dell'upload di un allegato"

**Importante!**  

Si chiede di non inserire dati sensibili dei cittadini, evitando qualsiasi nome, cognome, o codice fiscale. Non ci sono problemi invece nell'inserire dei codici di richiesta o identificativi di scheda.
Inoltre, si chiede di non inserire nessun dato relativo a configurazioni di sicurezza, quali certificati o password.
Si ricorda di inserire sempre:
* una descrizione accurata del comportamento o dell'errore, specificando che tipo di supporto si richiede;
* la data del test, l'ambiente usato (pre-produzione o produzione), codici di richiesta o identificativi da usare per verificare il sistema;
* nome, cognome e comune di riferimento dell’operatore.


Per il resto, ricordati che puoi scrivere in **grassetto**, inserire del codice:

```json
{
    "testataRichiesta": {
        "idComune": {{idComune}},
        "idOperazioneComune": "APP2022032210000",
        "dataOraRichiesta": "{{dataOraRichiesta}}",
        "nomeApplicativo": "{{nomeApplicativo}}",
        "versioneApplicativo": "{{versioneApplicativo}}",
        "fornitoreApplicativo": "{{fornitoreApplicativo}}"
    },
    "allegatoInput": {
        "contenuto": "JVBERi0xLjQK==",
        "protocollo": "31298/2023",
        "nomefile": "Allegato01.pdf",
        "tipoFile": "1",        
        "tipoAllegato": "2",
        "stato": "1"
    }
}
```

... oppure elenchi puntati:

   * punto
   * punto

... o titoli:

### Esempio titolo


--- TESTO DA ELIMINARE ---

