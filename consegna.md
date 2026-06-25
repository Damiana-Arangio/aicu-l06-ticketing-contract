# Consegna - Lezione 06

## Obiettivo

Trasformare la issue L05 in contratto iniziale, payload, error model, data sketch e Mermaid leggero.

Task:

```txt
Serve creare ticket dal supporto.
```

Come visto in aula, non chiedere ancora codice. Prima rendi controllabili input, output, errori e dati.

Questo passaggio serve professionalmente a:

- ridurre ambiguita' prima della patch;
- aiutare una review concreta;
- rendere verificabili gli errori;
- impedire all'AI di inventare campi e feature;
- preparare la ricerca degli entry point nella prossima lezione.

## Prima Di Compilare

Oggi userai cinque artefatti:

| Artefatto | Che cos'e' | A cosa serve | Output atteso | Errore tipico |
| --- | --- | --- | --- | --- |
| Contratto iniziale (contract sketch) | Accordo minimo su input, output e risposte | Sapere cosa chiedere al sistema prima del codice | 1 payload valido, 2 invalidi e risposte attese | Scrivere una specifica enorme |
| Payload | Esempio concreto di input | Rendere discutibile e verificabile la richiesta | JSON valido e JSON invalidi motivati | Scrivere esempi senza spiegare perche' passano o falliscono |
| Error model | Forma minima degli errori attesi | Rendere gli errori leggibili e verificabili | Caso, motivo e risposta attesa | Usare messaggi generici |
| Data sketch | Tabella dei campi e della loro fonte | Decidere quali dati servono davvero | Campi accettati, generati, respinti o mancanti | Accettare campi solo perche' li propone l'AI |
| Mermaid leggero | Diagramma minimo di relazione | Visualizzare i dati gia' motivati | Un diagramma piccolo, non definitivo | Progettare tutto il database |

Come visto in aula, riusa il percorso: prima definisci, poi controlli, poi scarti cio' che allarga lo scope.

### Stati Del Data Sketch

Usa questi stati in modo preciso:

| Stato | Quando usarlo |
| --- | --- |
| accettato | il campo arriva dall'input e serve al primo slice |
| generato | il campo viene creato dal sistema |
| respinto | il campo non entra nel primo slice o viola il fuori scope |
| mancante | il campo potrebbe servire, ma manca una fonte o decisione |

## Repository Di Lavoro

Lavora nel tuo fork della repo:

```txt
aicu-m02-l06-ticketing-contract
```

Prima di iniziare, importa dalla repo L05 solo l'artefatto richiesto:

```txt
aicu-m02-l05-ticketing-issue/output/issue-create-ticket.md
  -> lavoro-precedente/issue-create-ticket.md
```

Non copiare l'intera repo L05.

## Input

Usa:

```txt
template/contract-sketch-create-ticket.md
template/data-sketch-create-ticket.md
template/prompt-critica-contract.md
```

Puoi lavorare in Markdown, in una issue o in una nota locale.

## Cosa Fare

1. Riprendi la issue L05.
2. Scrivi una boundary map minima: UI, API, dati, verifica.
3. Compila il contratto iniziale.
4. Scrivi 1 payload valido.
5. Scrivi 2 payload invalidi.
6. Aggiungi risposta attesa per ogni payload.
7. Compila il data sketch.
8. Aggiungi un Mermaid leggero che visualizzi solo dati e relazione minima.
9. Usa il prompt di critica solo per trovare buchi, senza chiedere codice.
10. Aggiorna i template con le correzioni utili.

## Ordine Guidato

Procedi una sezione alla volta:

| Step | Output minimo | Check |
| --- | --- | --- |
| Issue importata | `lavoro-precedente/issue-create-ticket.md` | Non hai copiato tutta la repo |
| Payload valido | 1 JSON + risposta attesa | Spiega perche' e' valido |
| Payload invalido 1 | campo richiesto vuoto/mancante | Errore leggibile |
| Payload invalido 2 | valore fuori contratto | Errore leggibile |
| Data sketch | almeno 5 campi classificati | Ogni campo ha fonte |
| Mermaid leggero | 1 diagramma minimo | Non e' schema DB definitivo |

## Vincoli

- Non chiedere codice.
- Non scrivere specifiche API complete.
- Non progettare database o migration.
- Non usare Mermaid come schema database definitivo.
- Non aggiungere auth, allegati, notifiche, owner avanzato o dashboard.
- Non usare il caso aula come insieme di campi da copiare.
- Non chiedere chain-of-thought estesa: bastano evidenze brevi.

## Criteri Di Accettazione (Acceptance Criteria) Del Tuo Output

Il lavoro e' buono quando:

- contiene 1 payload valido e 2 invalidi;
- ogni payload ha risposta attesa;
- ogni errore ha motivo leggibile;
- almeno 5 campi sono classificati nel data sketch;
- ogni campo ha stato, motivo e fonte;
- il Mermaid mostra solo relazioni minime e campi gia' motivati;
- fuori scope / non-obiettivi (non-goals) della issue L05 restano rispettati;
- lascia chiaro cosa cercare nei file in L07.

## Pronto Quando

Hai finito quando puoi rispondere in 60 secondi:

```txt
Quale input accetto?
Quale input rifiuto?
Quale errore mi aspetto?
Quali dati servono davvero?
Quale campo ho rimandato o respinto?
```

## Micro-Task Post-Lezione

Input:

```txt
contract sketch e data sketch compilati
```

Azione:

```txt
rimuovi campi non motivati e aggiungi una nota per ogni campo respinto o rimandato.
```

Stop:

```txt
non aggiungere codice, schema DB, migration o PR.
```

## Fuori Scope

- Codice.
- Pull Request.
- Specifica API completa.
- Database schema.
- Migration.
- UI completa.
- Test automatici.
