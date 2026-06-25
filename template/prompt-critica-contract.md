# Prompt Critica Contract

## Prima Di Compilare

Questo prompt serve a far controllare all'AI buchi e incoerenze del contratto iniziale, non a farle decidere il contratto al posto tuo.

Usalo solo dopo una prima versione di contract sketch e data sketch.

L'output atteso e' una lista breve di problemi verificabili o la dichiarazione esplicita che non sono stati trovati problemi.

Rifiuta qualsiasi suggerimento che propone codice, specifiche API complete, schema database o feature fuori scope.

Usa questo prompt solo dopo aver scritto una prima versione di contract sketch e data sketch.

```txt
Leggi issue, contratto iniziale e data sketch.
Non proporre codice.
Non proporre specifiche API complete.
Non proporre schema database o migration.
Non allargare lo scope.

Cerca solo:
- payload non collegati alla issue;
- errori vaghi;
- campi non motivati;
- fuori scope / non-obiettivi (non-goals) violati;
- verifiche mancanti;
- assunzioni spacciate per fatti.

Rispondi in massimo 5 punti.
Per ogni punto indica:
- problema;
- perche' blocca la review;
- correzione suggerita del contratto iniziale o data sketch.

Se non trovi problemi, dichiaralo.
```

## Cosa Accettare

Accetta solo suggerimenti che migliorano:

- coerenza con la issue;
- payload;
- error model;
- data sketch;
- fuori scope / non-obiettivi (non-goals);
- verificabilita'.

## Cosa Rifiutare

Rifiuta suggerimenti che:

- propongono codice;
- aggiungono feature;
- introducono auth, allegati, notifiche, owner avanzato o dashboard;
- trasformano L06 in specifica API completa, migration o schema database.
