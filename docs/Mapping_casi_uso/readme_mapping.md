# Guida alla documentazione del file di mapping dei casi d'uso

Questo documento aiuta nella lettura della documentazione dei file di mapping dei casi d'uso (https://github.com/italia/ansc/blob/main/docs/Mapping_casi_uso).

Per ciascun caso d'uso è possibile consultare il relativo documento nel formato `csv` o `xlsx` contenente una tabella
contenente le colonne a seguire:

- **Sezione**: definisce il nome della sezione o specifica se si tratti di allegati o formule.
- **Campo** definisce il nome del campo o la descrizione dell'allegato o la formula assegnata al caso d'uso.
- **Obbligatorio**: definisce l'obbligatorietà del "campo" appartenente alla "sezione".
- **Binding Object**: definisce il percorso per arrivare alla proprietà.
- **Binding Field**: definisce il nome dell'oggetto da valorizzare.
- **Note obbligatorietà Formule**: definisce per quale formula la proprietà è necessaria.
- **Condizioni obbligatorietà**: definisce la condizione per cui l'elemento del record è obbligatorio; l'elemento può essere un allegato, una formula o un campo di una sezione.
- **Si può ignorare la sezione per**: se l'elemento di riferimento è un allegato o una formula, la condizione definisce l'obbligatorietà dell'elemento. Se invece ci si riferisce ad un campo di una sezione (es. campo cognome della sezione soggetto), la condizione, quando verificata, permette di ignorare il record reputando il campo non obbligatorio.

Prendendo come esempio il documento [Trascr_012.csv (v1.28.3)](https://github.com/italia/ansc/blob/v1.28.3/docs/Mapping_casi_uso/trascrizioni/Trascr_012.csv),
analizziamo la riga [11](https://github.com/italia/ansc/blob/1dc0a1fb61c234c355e4ce1477d6a3ceb172c41c/docs/Mapping_casi_uso/trascrizioni/Trascr_012.csv#L11) (vedi Tabella 1).

| Nome colonna                                                | Valore                                                 | Significato                                  |
|:------------------------------------------------------------|:-------------------------------------------------------|:---------------------------------------------|
| Sezione                                                     | Dati generali                                          | Nome della sezione di appartenenza del campo |
| Campo                                                       | Nuovo cognome                                          | Nome del campo                               |
| Obbligatorio                                                | SI                                                     | Obbligatorietà del campo                     |
| Binding Object                                              | evento.trascrizioneNascita                             | Binding object del campo                     |
| Binding Field                                               | nuovoCognome                                           | Binding field del campo                      |
| Condizioni obbligatorietà > Si puo' ignorare la sezione per | evento.trascrizioneNascita.sceltaCognome,in,(7,8,9,10) | Condizione di non visibilità della sezione   |

Tabella 1 - Esempio di riga del documento Trascr_012.csv

Se la proprietà `evento.trascrizioneNascita.sceltaCognome = 6`, il campo `evento.trascrizioneNascita.nuovoCognome` sarà richiesto obbligatoriamente.

Se `evento.trascrizioneNascita.sceltaCognome = 7` il campo in questione si può ignorare e non è richiesto in input

> _Talvolta, per esigenze di configurazione, la documentazione mostra più sezioni con lo stesso nome e/o con campi con lo stesso **binding object** e **binding filed**._

Con riferimento al documento Trascr_012.csv (https://github.com/italia/ansc/blob/main/docs/Mapping_casi_uso/trascrizioni/Trascr_012.csv) è possibile notare che la sezione
**Dati generali** mostra ventuno record che rappresentano diverse condizioni di obbligatorietà.

Considerando quindi la ridefinizione della colonna **Condizioni obbligatorietà** in **Si può ignorare la sezione per**
è possibile individuare cinque possibili alternative di valorizzazione della sezione in questione:

1. evento.trascrizioneNascita.sceltaCognome,in,(7,8,9,10)
2. evento.trascrizioneNascita.sceltaCognome,in,(6,7,9,10)
3. evento.trascrizioneNascita.sceltaCognome,in,(6,8,9,10)
4. evento.trascrizioneNascita.sceltaCognome,in,(6,7,8,10)
5. evento.trascrizioneNascita.sceltaCognome,in,(6,7,8,9)

Se `evento.trascrizioneNascita.sceltaCognome = 6`, la condizione **1** di ignorare la sezione risulta non soddisfatta e
sarà richiesta la proprietà.

Risultano invece soddisfatte tutte le altre quattro condizioni **2**, **3**, **4** e **5** di ignorare la relativa proprietà.

Se `evento.trascrizioneNascita.sceltaCognome = 7`, risulta non soddisfatta la condizione **3** di ignorare la sezione e
sarà richiesta la proprietà.

Risultano invece soddisfatte tutte le altre quattro condizioni **1**, **2**, **4** e **5** di ignorare la proprietà;
e così via.