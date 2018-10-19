# Laboratorio di informatica (3/12)
### Prof. Stefano Carrazza - Corso C - 2018/19

**Riassunto:** Esercizi di base in C++: strings, cin, cout, file IO, if e else.

Prima di iniziare suggeriamo di create una cartella per la Lezione 3 in cui potete salvare tutti i files che saranno creati per gli esercizi.
```bash
cd ~/           # ci porta alla home directory
mkdir lezione3  # crea la directory lezione3 sulla vostra home
cd lezione3     # entrate dentro la cartella lezione3
```
dopodiché creare un `makefile` con targets
- `all`: compila tutti i programmi di questa dispensa.
- `clean`: elimina tutti i programmi creati da `all`.

Esempio di `makefile`:
```makefile
all: prog1 # programma2 program...

prog1: esercizio1.cc
  g++ -o prog1 esercizio1.cc
  # oppure: g++ -o $@ $<

clean:
  rm prog1
```
in questo modo tutti programmi saranno compilati eseguendo il commando da terminale:
```bash
$ make
```
mentre tutti i programmi saranno eliminati eseguendo il commando da terminale:
```bash
$ make clean
```

## Esercizio 1 - Incremento / decremento

Scrivere un programma in C++ in cui:

1. Il programma vi chiede di introdurre un numero intero `n`.

2. Calcolare l'incremento e il decremento di `n` usando gli operatori `++` e `--`.

3. Calcolare la divisione e il modulo (resto) di `n` per un `int r = 2;`.

5. Stampare tutti i risultati su schermo.

## Esercizio 2 - Numeri pari e dispari

Scrivere un programma che prende un numero intero e determina se si tratta di un
numero pari oppure dispari. Per farlo utilizzare l'operatore modulo assieme ad
operatori di selezione two-way (`if`, `else`).

## Esercizio 3 - string e char

Scrivere un programma in C++ in cui:

1. Vi chiede come input da terminale il vostro nome, cognome e numero matricola. Utilizzare variabili di tipo `char nome[20];` per il nome, `string` per il cognome e `int` per il numero matricola. Implementare l'interfaccia nel modo seguente:
```text
Nome     :
Cognome  :
Matricola:
```

2. Stampare con `cout` una riga con la sintassi seguente:
```bash
<cognome>, <nome> è registrato con numero matricola: <matricola>.
```

## Esercizio 4 - File output

Adattare l'esercizio precedente in modo che l'output finale sia scritto su un
file chiamato `risultato.dat`.

1. Creare una copia dell'esercizio precedente.
2. Implementare con `fstream` la creazione del file di output con il metodo `open()`,
seguito dal test di successo con il metodo `good()`.
3. Scrivere il contenuto su schermo e file.
4. Chiudere il file con il metodo `close()`.

## Esercizio 5 - File input

Adattare l'esercizio precedente in modo che l'input sia letto da un file chiamato
`myinput.dat` con il contenuto seguente:
```
<vostro nome>
<vostro cognome>
<vostro numero di matricola>
```

1. Creare una copia dell'esercizio precedente.
2. Implementare con `fstream` la apertura del file `myinput.dat`.
3. Leggere i dati da file.
4. Chiudere il file.
5. Stampare i risultati su schermo e file `risultato.dat`.

## Esercizio 6 - Equazione quadratica

Scrivere un programma in C++ dove viene risolta l'equazione quadratica
`a x^2 + b x + c = 0` per tutti i discriminanti (>, < e = 0) e dove le variabili
`a`, `b` e `c` vengono assegnate tramite `cin`.

Verificare l'implementazione per i seguenti coefficienti:
- `a = 2`, `b = 5`, `c = 2` -> soluzione `x1 = -0.5` e `x2 = -2`.
- `a = 4`, `b = -4`, `c = 1` -> soluzione `x1,2 = 0.5`.
- `a = 1`, `b = 4`, `c = 5` -> soluzione `x1 = -2 + i` e `x2 = -2 - i`.

## Esercizio 7 - Scelta telaio bicicletta

Scrivere un programma in C++ che in base all'età, altezza e peso dell'atleta (introdotti da riga di commando) propone
una taglia di bicicletta (XS,S,M,L,XL) seguendo i criteri:

- meno o uguale a 10 anni: XS
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

## Esercizio 8 - Conversione temperatura 2

Scrivere un programma in C++ in cui sia possibile convertire una temperature da 
Celsius a Kelvin oppure Fahrenheit (usando two-way selection `if` / `else`).

Permettere all'utente di introdurre la temperatura
di input in Celsius usando `cin`.

Scrivere le formule di conversione:
```
T(Kelvin) = T(Celsius) + 273.15
T(Fahrenheit) = T(Celsius) * 9 / 5 + 32.0
```
in termini di funzioni:
```c++
double Tc_to_Tk(double Tc) 
{ 
  // convertire Celsius to Kelvin 
  return // implementare formula
}

double Tc_to_Tf(double Tc)
{ 
  // Celsius to Fahrenheit
  return // implementare formula
}
```
che verranno chiamate direttamente dal `main`. Verificare le seguenti conversioni:
- 20 °C -> 68.0 °F
- 20 °C -> 293.15 K
