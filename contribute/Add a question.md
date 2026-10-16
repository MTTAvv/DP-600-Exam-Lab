## Aggiungere una domanda

1. Apri `index.html` con un editor, ad esempio VS Code, e cerca `const DATA=`.
2. Vai alla fine dell'elenco, prima di `const CASES=`.
3. Aggiungi una virgola dopo l'ultimo oggetto e incolla la nuova domanda.
4. Salva il file e aggiorna il repository.

### Domanda a scelta singola o multipla

```json
{
  "number": 200,
  "case": "",
  "type": "choice",
  "prompt": "Testo della domanda?",
  "options": [
    {"k": "A", "t": "Prima opzione"},
    {"k": "B", "t": "Seconda opzione"},
    {"k": "C", "t": "Terza opzione"}
  ],
  "answer": ["B"],
  "answer_text": "B",
  "answer_images": [],
  "explanation": "Perché B è corretta.",
  "note": "",
  "recon": false,
  "reason": "Suggerimento per ragionare sulla risposta.",
  "refs": [
    {
      "file": "3-get-data.md",
      "title": "3.4 Notebook",
      "anchor": "34-notebook"
    }
  ]
}
```

Per la scelta singola usa una sola lettera in `answer`; per quella multipla, inserisci tutte le risposte corrette, ad esempio `["B", "D"]`.

### Domanda Sì/No

```json
{
  "type": "yesno",
  "statements": ["Prima affermazione.", "Seconda affermazione."],
  "answer": ["Sì", "No"]
}
```

### Menu a tendina / Completamento codice

```json
{
  "type": "slots",
  "slots": [
    {
      "label": "Spazio [1]",
      "options": ["COALESCE", "ISNULL", "NULLIF"],
      "answer": "COALESCE"
    }
  ],
  "answer": ["COALESCE"]
}
```

Nel campo `prompt`, usa `[1]`, `[2]` e così via per indicare i punti da completare, ad esempio `SELECT [1](a, b) FROM t`.

### Formattazione del testo

- **A capo:** `\n`; nuovo paragrafo: `\n\n`.
- **Virgolette:** usa `\"`.
- **Elenchi:** separa le voci con `\n` e usa `- ` all'inizio.
- **Codice:** i paragrafi che iniziano con istruzioni come `SELECT`, `CREATE`, `df.` o `EVALUATE` vengono formattati come codice.
- **Tabelle:** usa la sintassi Markdown.
- **Immagini:** inserisci `[[img:image200.png]]` nel `prompt` e salva il file in `Photos/`, usando il numero della domanda nel nome.
- **Case study:** imposta `case` su `"Contoso"` o `"Litware"`. Per le domande normali usa `""`.

### Attenzione

- Ogni `number` deve essere univoco.
- Il filtro per argomenti usa il primo elemento di `refs`.
- `anchor` deriva dal titolo della sezione in minuscolo, senza punteggiatura e con i trattini al posto degli spazi. Ad esempio, `3.4 Notebook` diventa `34-notebook`.
- Il riferimento completo segue il formato `Course material/<file>#<anchor>`.
- Se la pagina rimane vuota, controlla la sintassi JSON: spesso manca una virgola o una virgoletta. VS Code evidenzia gli errori; in alternativa, apri la console del browser con `F12`.
