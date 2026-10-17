# PUM — Zadanie 1: Eksploracja danych w Kedro

Projekt na przedmiot PUM (PJATK).

Celem Zadania 1 jest wczytanie dwóch zbiorów danych
do Kedro, wykonanie analizy EDA, wizualizacji
oraz przedstawienie wniosków.

Zgodnie z założeniami kursu ten sam projekt może
być kontynuowany w Zadaniu 2. Obecna wersja
obejmuje wyłącznie Zadanie 1.

## Zbiory danych

| Zbiór | Rekordy | Kolumny | Zmienna celu |
|---|---:|---:|---|
| Titanic | 891 | 15 | survived |
| Iris | 150 | 5 | target |

Źródła:
- Titanic: https://github.com/mwaskom/seaborn-data
- Iris: scikit-learn, load_iris

## Wykonane czynności

- Utworzenie projektu Kedro
- Rejestracja CSV w Kedro Data Catalog
- Analiza struktury, typów i braków danych
- Obliczenie statystyk opisowych
- Analiza rozkładów i zależności
- Przygotowanie 9 wykresów
- Opracowanie raportu EDA

## Najważniejsze wnioski

**Titanic:** Przeżywalność wynosi 38,38%.
Kobiety oraz pasażerowie pierwszej klasy
przeżywali częściej. W zbiorze występują
liczne braki danych w kolumnach age i deck.

**Iris:** Zbiór nie ma brakujących wartości.
Długość i szerokość płatków są silnie
skorelowane (r = 0,963).

## Struktura projektu

- `conf/base/catalog.yml` — konfiguracja danych
- `data/01_raw/` — dwa pliki CSV
- `data/08_reporting/` — 9 wykresów PNG
- `notebooks/eda.ipynb` — analiza EDA
- `raport.md` — wyniki i wnioski
- `pyproject.toml` — konfiguracja projektu

## Uruchomienie

Python 3.12:

```bash
python3.12 -m venv .venv
source .venv/bin/activate
python -m pip install -e .
kedro jupyter lab
```

Otwórz `notebooks/eda.ipynb`, wybierz kernel
Kedro i uruchom komórki od początku do końca.

Wykresy zapisywane są w `data/08_reporting/`.
