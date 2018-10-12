# Laboratorio di informatica (2/12)
### Prof. Stefano Carrazza - Corso C - 2018/19

**Riassunto:** Esercizi di base per la programmazione in C++.

Prima di iniziare suggeriamo di create una cartella per la Lezione 2 in cui potete
salvare tutti i files che saranno creati per gli esercizi.

*Esempio:* `cd ~/; mkdir lezione2; cd lezione2;`

## Esercizio 1 - Hello World in C++

Scrivere un programma in C++ in cui si mostri su schermo la frase "Hello Word!".

1. Aprire un terminale e creare un nuovo file chiamato `esercizio1.cc`, con
`gedit` un programma in C++ che mostri su schermo la frase "Hello World!".

2. Compilare usando:
```bash
g++ -o prog1 esercizio1.cc
```
dove `g++` è il compiler per C++, `-o` l'opzione per determinare il nome del
eseguibile che sarà creato da `g++`.

3. Eseguire il programma con:
```bash
./prog1
```
e controllare l'output.

## Esercizio 2 - Calcolo area e perimetro del rettangolo

Scrivere un programma in C++ in cui si calcola l'area e perimetro di un rettangolo.

1. Aprire un nuovo file `esercizio2.cc`, dichiarare delle variabili di tipo doppia precisione (`double`) per la `base` e `altezza` del rettangolo.

2. Assegnare una `base` di `5.0` e una altezza di `2.0`.

3. Scrivere le formule per l'area e perimetro del rettangolo usando variabili C++.

4. Stampare su schermo i risultati usando `cout`.

5. Compilare il codice con `g++`, chiamando l'eseguibile `prog2`.

6. Eseguire il codice e controllare l'output.

## Esercizio 3 - Makefile

Scrivere un semplice file `makefile` in cui:

1. gli esercizi precedenti vengono compilati con:
```bash
make prog1
make prog2
```

2. tutti gli esercizi vengono compilati con:
```bash
make
```

3. `prog2` viene eseguito automaticamente con:
```bash
make esegui
```

4. tutti i binary generati dal commando `make` vengono eliminati con:
```bash
make clean
```

## Esercizio 4 - Sistemare un programma

Identificare e correggere gli errori di sintassi presenti nel seguente programma,
anche con l'aiuto dell'output prodotto dal compiler `g++` dopo aver copiato il
contenuto sul file `esercizio4.cc`:
```c++
// Contenuto file esercizio4.cc
#include <iostream>
#include <cmath>
using namespace std

int main()
{
  const double angolo = 9;
  const int a = 2, b = 3, somma = 0;  

  somma=a+b

  cout << "sin(9) = " <<sin(angolo) << endl;
  cout << "somma = " << somma << "\n";

return   0;
}
```
Identificare righe di codice che potrebbero essere migliorate da un'opportuna
indentazione.

## Esercizio 5 - Input/output

Copiare il file `esercizio2.cc` (area/perimetro rettangolo) in un nuovo file `esercizio5.cc` e aggiornare il makefile con il nuovo programma, i.e. `prog5`.

Modificare il programma in modo che le variabili che corrispondono alla base
e altezza del triangolo vengano lette da terminale con chiamate a `cin`.

## Esercizio 6 - Notazione per cout

Copiare il file dell'esercizio precedente in `esercizio6.cc` e aggiornare il makefile.

Stampare con `cout` i risultati dell'area e perimetro usando 10 cifre significative per cout, usando la notazione `fixed` e poi quella `scientific`.

Stampare con `cout`, in qualunque notazione, l'area e perimetro del rettangolo
sulla stessa riga, separati da una tabulazione `\t`.

## Esercizio 7 - Conversione temperatura 1

Scrivere un programma in C++ in cui sia possibile convertire una temperature da
Celsius a Kelvin usando l'equazione:
```
T(Kelvin) = T(Celsius) + 273.15
```
dove l'utente puo introdurre la temperatura di input in Celsius usando `cin`.

Verificare le seguenti conversioni:
- 20 °C -> 293.15 K
- 30 °C -> 303.15 K

## Esercizio 8 - String e char

Scrivere un programma in C++ in cui:

1. Vi chiede come input da terminale il vostro nome, cognome e numero matricola. Utilizzare variabili di tipo `char nome[20];` per il nome, `string` per il cognome e `int` per il numero matricola.

2. Stampare con `cout` una riga con la sintassi seguente:
```bash
<cognome>, <nome> è registrato con numero matricola: <matricola>.
```

## Esercizio 9 - Sizeof

Scrivere un programma in C++ che stampa su schermo le dimensioni in bytes per i tipi
 `int, double, long double, float, bool` usando la funzione `sizeof`.

 Per ogni type, stampare una riga di tipo:
 ```bash
 <type> size is :<sizeof> bytes.
 ```

## Esercizio 10 - Incremento / decremento

Scrivere un programma in C++ in cui:

1. Il programma che vi chiede di introdurre un numero intero.

2. E in seguito vi propone 2 opzioni da scegliere tra:
```bash
Per incrementare di uno scegliere opzione 1
Per decrementare di uno scegliere opzione 2
Opzione scelta:
```

3. Implementare una condizione `if / else` per distinguere opzione 1 da 2.

4. Per ogni opzione implementare l'incremento e decremento usando gli operatori
`++` e `--`.

5. Stampare i risultati su schermo.

## Esercizio 11 - Equazione quadratica

Scrivere un programma in C++ dove viene risolta l'equazione quadratica
`a x^2 + b x + c = 0` per tutti i discriminanti (>, < e = 0) e dove le variabili
`a`, `b` e `c` vengono assegnate tramite `cin`.

Verificare l'implementazione per i seguenti coefficienti:
- `a = 2`, `b = 5`, `c = 2` -> soluzione `x1 = -0.5` e `x2 = -2`.
- `a = 4`, `b = -4`, `c = 1` -> soluzione `x1,2 = 0.5`.
- `a = 1`, `b = 4`, `c = 5` -> soluzione `x1 = -2 + i` e `x2 = -2 - i`.

## Esercizio 12 - Conversione temperatura 2

Scrivere un programma in C++ in cui sia possibile convertire una temperature da
Celsius a Kelvin oppure Fahrenheit.

Permettere all'utente di introdurre la temperatura
di input in Celsius usando `cin`.

Scrivere le formule di conversione:
```
T(Kelvin) = T(Celsius) + 273.15
T(Fahrenheit) = T(Celsius) * 9 / 5 + 32.0
```
in termini di funzioni:
```c++
double Tc_to_Tk(double Tc); // Celsius to Kelvin
double Tc_to_Tf(double Tc); // Celsius to Fahrenheit
```
che verranno chiamate direttamente dal `main`. Verificare le seguenti conversioni:
- 20 °C -> 68.0 °F
- 20 °C -> 293.15 K
