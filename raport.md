# Raport EDA - Zadanie 1 PUM

## 1. Cel analizy

Celem zadania jest przeprowadzenie eksploracyjnej analizy
dwoch zbiorow danych w projekcie Kedro: Titanic i Iris.
Analiza obejmuje strukture danych, statystyki opisowe,
braki danych, duplikaty oraz podstawowe wizualizacje.

## 2. Zbior Titanic

Zrodlo: seaborn-data (GitHub).

### Charakterystyka
- Liczba rekordow: 891
- Liczba kolumn: 15
- Zmienna celu: survived (0 - nie przezyl, 1 - przezyl)

### Najwazniejsze zmienne
- sex - plec pasazera
- pclass - klasa biletu
- age - wiek pasazera

Zmienne te moga byc przydatne do analizy czynnikow
zwiazanych z prawdopodobienstwem przezycia.

### Jakosc danych
- age: 177 brakujacych wartosci (19,87%)
- deck: 688 brakujacych wartosci (77,22%)
- embarked: 2 brakujace wartosci
- embark_town: 2 brakujace wartosci
- 107 powtarzajacych sie wierszy

Powtarzajace sie wiersze nie musza oznaczac bledow,
poniewaz dane nie zawieraja unikalnego identyfikatora
pasazera. Nie nalezy usuwac ich automatycznie.

### Wnioski
Odsetek ocalalych wynosi okolo 38,4%.
Kobiety przezywaly znacznie czesciej niz mezczyzni.
Najwiecej pasazerow podrozowalo trzecia klasa.
Przed przyszlym modelowaniem nalezy rozwazyc
uzupelnienie brakow wieku i obsluge kolumny deck.

## 3. Zbior Iris

Zrodlo: scikit-learn, load_iris.

### Charakterystyka
- Liczba rekordow: 150
- Liczba kolumn: 5
- Trzy gatunki kwiatow, po 50 obserwacji
- Zmienna celu: target (0, 1 lub 2)

### Najwazniejsze zmienne
- petal length (cm) - dlugosc platka
- petal width (cm) - szerokosc platka
- target - gatunek kwiatu

### Jakosc danych
- Brak brakujacych wartosci
- 1 powtarzajacy sie wiersz
- Wszystkie cechy pomiarowe sa numeryczne

### Wnioski
Srednia dlugosc platka wynosi okolo 3,76 cm.
Wymiary platkow roznia sie miedzy gatunkami.
Setosa jest wyraznie oddzielona od pozostalych
gatunkow na wykresie zaleznosci wymiarow platkow.
Versicolor i Virginica czesciowo sie nakladaja.

## 4. Porownanie zbiorow

Titanic jest wiekszym i bardziej zroznicowanym
zbiorem. Zawiera dane liczbowe, kategoryczne
oraz liczne braki wartosci.

Iris jest mniejszy, kompletny i zawiera glownie
numeryczne pomiary. Klasy sa rownomiernie rozlozone.

Titanic nadaje sie do analizy przezywalnosci,
natomiast Iris do klasyfikacji gatunkow kwiatow.

## 5. Mozliwe wykorzystanie w Kedro

Oba datasety nie posiadaja wspolnego klucza
ani logicznej relacji umozliwiajacej polaczenie
ich rekordow w jedna tabele.

W przyszlosci mozna utworzyc dwie osobne galezie
pipeline Kedro, korzystajace ze wspolnych zasad
przygotowania danych.

Dla Titanica potrzebna bedzie obsluga brakow
danych i kodowanie zmiennych kategorycznych.
Dla Iris wystarczy prostsze przygotowanie
cech numerycznych.

Wyniki obu galezi mozna zestawic na poziomie
raportowania lub porownania modeli.

## 6. Wykresy

### Titanic
![Rozklad wieku](data/08_reporting/01_titanic_wiek.png)

![Przezycie](data/08_reporting/02_titanic_przezycie.png)

![Plec](data/08_reporting/03_titanic_plec.png)

### Iris
![Dlugosc platkow](data/08_reporting/04_iris_platki.png)

![Gatunki](data/08_reporting/05_iris_gatunki.png)

![Zaleznosc cech](data/08_reporting/06_iris_zaleznosc.png)
