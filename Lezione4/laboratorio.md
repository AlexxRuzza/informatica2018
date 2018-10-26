# Laboratorio di informatica (4/12)
### Prof. Stefano Carrazza - Corso C - 2018/19

**Riassunto:** Esercizi di base in C++: if e else, switch e for.

Prima di iniziare suggeriamo di create una cartella per questa lezione in cui potete salvare tutti i files che saranno creati per gli esercizi.
```bash
cd ~/           # ci porta alla home directory
mkdir lezione4  # crea la directory lezione4 sulla vostra home
cd lezione4     # entrate dentro la cartella lezione4
```
dopodiché creare un `makefile` con le istruzioni di compilazione per tutti gli esercizi.

## Esercizio 1 - Conversioni temperature

Scrivere un programma in C++ in cui sia possibile convertire una temperature da
Celsius a Kelvin oppure Fahrenheit (usando two-way selection `if` / `else`).

1. Chiedere all'utente di introdurre da terminale la temperatura di input in Celsius usando `cin`.

2. Salvare il valore in una variabile di tipo `double`.

3. Chiedere all'utente:
```text
Premere 1 per conversione a Kelvin.
Premere 2 per conversione a Fahrenheit.
Opzione scelta: <valore_da_cin>
```

4. Salvare la scelta dell'utente in una variabile di tipo `int`, e creare la
condizione `if/else` corrispondente.

5. Implementare le formule di conversione per entrambe opzioni:
```
T(Kelvin) = T(Celsius) + 273.15
T(Fahrenheit) = T(Celsius) * 9.0 / 5.0 + 32.0
```

6. Stampare su schermo il risultato della conversione seguendo il formatto:
```text
T(Celsius) = <valore_di_input> -> T(<scelta>) = <valore_convertito>
```

Verificare le seguenti conversioni:
- 20 °C -> 68.0 °F
- 20 °C -> 293.15 K

## Esercizio 2 - Equazione quadratica

Scrivere un programma in C++ dove viene risolta l'equazione quadratica
`a x^2 + b x + c = 0` per tutti i discriminanti (>, < e = 0) e dove le variabili `a`, `b` e `c` vengono assegnate tramite `cin`.

1. Chiedere all'utente di introdurre 3 numeri di tipo `double`.

2. Calcolare il discriminante `D = b^2 - 4ac` usando la funzione `std::pow`.

3. Creare una condizione `if/else if/else` corrispondente ai 3 casi possibili
per il discriminante.

4. Calcolare le soluzioni `x1` e `x2` utilizzando la nota formula quadratica.
Notare che per `D < 0`, la funzione `std::sqrt()` opera in campo reale, quindi il suo argomento dovrà essere positivo, anche in questo caso suggeriamo di separare e calcolare a parte la componente reale e immaginaria delle soluzioni.

Verificare l'implementazione per i seguenti coefficienti:
- `a = 2`, `b = 5`, `c = 2` -> soluzione `x1 = -0.5` e `x2 = -2`.
- `a = 4`, `b = -4`, `c = 1` -> soluzione `x1,2 = 0.5`.
- `a = 1`, `b = 4`, `c = 5` -> soluzione `x1 = -2 + i` e `x2 = -2 - i`.

## Esercizio 3 - Scelta telaio bicicletta

Scrivere un programma in C++ che in base all'età, altezza e peso dell'atleta (introdotti da riga di commando) propone
una taglia di bicicletta (XS,S,M,L,XL) seguendo i criteri:

- minore o uguale a 10 anni: XS
- tra 10 a 18 anni (compresi):
  - altezza minore uguale a 1.10m: XS
  - altezza tra 1.10m e 1.30m (compreso) e peso minore di 40kg (compreso): S
  - altezza tra 1.10m e 1.30m (compreso) e peso maggiore di 40kg: M
  - altezza tra 1.30m e 1.60m (compreso): M
  - altezza maggiore di 1.70m: L
- più di 18 anni:
  - altezza minore di 1.40m (compreso) oppure peso minore di 40kg (compreso): XS
  - altezza tra 1.40m e 1.60m (compreso): S
  - altezza tra 1.60m e 1.70m (compreso): M
  - altezza tra 1.70m e 1.90m (compreso): L
  - altezza maggiore di 1.90m: XL

Implementare le condizioni utilizzando condizioni di selezione `if`, `else if`, `else`.

## Esercizio 4 - switch

Utilizzare la struttura di controllo `switch` per stampare il vostro nome a partire dal numero matricola.

1. Creare una variabile `int` per lo storage del numero di matricola.

2. Chiedere da terminale il numero matricola.

2. Creare una condizione `switch` in cui nel caso del vostro numero
matricola stampa il vostro nome, mentre nel caso di detault stampa il
messaggio errore: "Matricola non trovata".

## Esercizio 5 - Calcolare media (input da terminale)

Scrivere un programma in C++ capace di calcolare la media di numeri introdotti
da terminale.

1. Chiedere all'utente quanti numeri vuole introdurre. Salvare tale valore in
una variabile di tipo `int n`.

2. Costruire un loop usando l'istruzione `for` che chiede all'utente di introdurre un numero di tipo `double`.

3. Creare una variabile `double sum = 0;` e incrementarla all'interno del loop usando i nuovi valori introdotti dall'utente.

4. Stampare su schermo la media di tutti i numeri come `sum/n`.

## Esercizio 6 - Calcolare media (input da file)

1. Scaricare il file con dati copiando e incollando il commando seguente su terminale:
```bash
wget https://raw.githubusercontent.com/scarrazza/informatica2018/master/Lezione4/data.dat
```
I dati contengono 1000 numeri corrispondenti a misure fatte in laboratorio della costante di accelerazione di gravità `g`.

2. Leggere tutti i numeri da file usando un loop `for` infinito, controllato dalla condizione `eof`.

3. Salvare in una variable `double sum = 0.0;` la somma incrementale dei numeri.

4. Fare lo stesso per il conteggio del numero totale di elementi.

5. Calcolare media e stamparla su schermo, verificare che il suo valore sia vicino a `g=9.7803184`.
