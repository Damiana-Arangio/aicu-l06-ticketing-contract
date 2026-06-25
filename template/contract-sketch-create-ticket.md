# Contratto Iniziale (Contract Sketch) - Create Ticket

## Prima Di Compilare

Un contratto iniziale (contract sketch) e' una descrizione leggera di input, output e risposte attese.

Serve a rendere verificabile `create ticket` prima di chiedere codice all'AI.

Compila solo la superficie minima:

- cosa entra;
- cosa esce;
- cosa viene rifiutato;
- quale errore ti aspetti.

Non trasformarlo in una specifica API completa, uno schema di un database o un piano di una patch.

Quando compili, ogni esempio deve rispondere (almeno) a tre domande:

- perche' questo input e' valido o invalido?
- quale risposta mi aspetto?
- quale parte della issue o del fuori scope giustifica la scelta?

## Request

```txt
Serve creare ticket dal supporto.
```

## Boundary Map

| Superficie | Cosa riguarda | Nota |
| --- | --- | --- |
| UI | [cosa inserisce o vede l'utente] | [nota] |
| API / azione | [input e output attesi] | [nota] |
| Dati | [campi conservati o generati] | [nota] |
| Verifica | [come controlli il comportamento] | [nota] |

## Action

Per questo slice, `create ticket` significa:

```txt
[scrivi una decisione minima e verificabile]
```

## Payload Valido

```json
{
}
```

Perche' e' valido:

- [motivo 1]
- [motivo 2]

## Risposta Attesa Di Successo

```txt
[status o risultato atteso]
```

Campi attesi:

- [campo generato o restituito]
- [campo confermato]

## Payload Invalido 1

```json
{
}
```

Motivo del rifiuto:

```txt
[perche' e' invalido]
```

Risposta attesa:

```txt
[status o errore atteso]
```

## Payload Invalido 2

```json
{
}
```

Motivo del rifiuto:

```txt
[perche' e' invalido]
```

Risposta attesa:

```txt
[status o errore atteso]
```

## Error Model Minimo

| Caso | Motivo | Risposta attesa |
| --- | --- | --- |
| Campo richiesto mancante o vuoto | [motivo] | [errore] |
| Valore fuori contratto | [motivo] | [errore] |

## Non-Goals Confermati

- [cosa resta fuori scope]
- [cosa non chiedere all'AI]
- [cosa rimandare]


