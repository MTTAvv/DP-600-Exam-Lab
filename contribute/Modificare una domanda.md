## Modificare o eliminare una domanda

Tutte le domande sono definite in `index.html`, all'interno dell'array `DATA`.

### Modificare una domanda

1. Apri `index.html` con VS Code e cerca `const DATA=`.
2. Cerca il campo `number` della domanda che vuoi modificare, ad esempio `"number": 200`.
3. Modifica i campi necessari (`prompt`, `options`, `answer`, `explanation` e così via), mantenendo la struttura JSON.
4. Salva il file e aggiorna il repository.

**Attenzione:** se modifichi le opzioni o il testo della domanda, ricordati di aggiornare anche `answer`, `answer_text` e `explanation`, se necessario.

### Eliminare una domanda

1. Apri `index.html` e cerca `const DATA=`.
2. Individua l'oggetto della domanda tramite il suo `number`.
3. Elimina l'intero oggetto, comprese le parentesi graffe `{ }`.
4. Controlla le virgole tra gli oggetti: non devono esserci virgole mancanti o in eccesso.
5. Salva il file e aggiorna il repository.

**Esempio:** per eliminare la domanda con numero `200`, rimuovi tutto l'oggetto che contiene `"number": 200`, senza eliminare le domande vicine.

### Controlli finali

- Il campo `number` deve rimanere univoco per ogni domanda.
- Verifica che `answer` corrisponda alle opzioni disponibili e che la spiegazione sia aggiornata.
- Se la domanda contiene immagini, controlla che gli eventuali file non siano utilizzati anche da altre domande prima di eliminarli.
- Se la pagina rimane vuota, controlla la sintassi in VS Code oppure apri la console del browser con `F12`.

Infine, salva le modifiche e fai il commit e il push sul repository per pubblicarle.

FARE SEMPRE UN BACKUP PRIMA DI EFFETTUARE QUALSIASI MODIFICA
