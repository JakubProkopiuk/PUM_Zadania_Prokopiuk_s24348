# PUM - Zadania 1 i 2

Projekt przygotowany na przedmiot PUM na PJATK.

Repozytorium jest przeznaczone na Zadanie 1 i Zadanie 2.
Zadanie 1 obejmuje eksploracyjna analize danych (EDA).
Zadanie 2 bedzie kontynuacja projektu o etap modelowania.

## Zadanie 1 - Analiza danych

W projekcie wykorzystano dwa zbiory danych:

### Titanic
- Zrodlo: seaborn-data (GitHub)
- 891 rekordow i 15 kolumn
- Zmienna celu: survived
- Analiza wieku, przezywalnosci i plci pasazerow
- Zidentyfikowano braki danych, m.in. w kolumnach age i deck

### Iris
- Zrodlo: scikit-learn
- 150 rekordow i 5 kolumn
- Zmienna celu: target
- Analiza wymiarow platkow i gatunkow kwiatow
- Brak brakujacych wartosci

## Wnioski z EDA

Titanic zawiera dane numeryczne i kategoryczne,
a takze liczne braki danych.
Plec pasazera wykazuje wyrazny zwiazek z przezyciem.

Iris zawiera kompletne dane numeryczne.
Wymiary platkow pomagaja rozrozniac gatunki kwiatow.

## Struktura projektu

- `conf/base/catalog.yml` - konfiguracja Kedro Data Catalog
- `data/01_raw/` - surowe pliki CSV
- `data/08_reporting/` - szesc wykresow PNG
- `notebooks/eda.ipynb` - kod analizy danych
- `raport.md` - szczegolowy raport i wnioski
- `src/` - struktura projektu Kedro

## Uruchomienie

Projekt wykorzystuje Python 3.12 i Kedro 1.7.

Po utworzeniu i aktywowaniu srodowiska Python:

```bash
python -m pip install -e .
python -m pip install "kedro-datasets[pandas-csvdataset]"
python -m pip install matplotlib seaborn scikit-learn ipykernel
kedro jupyter lab
```

Nastepnie otworz `notebooks/eda.ipynb`
i uruchom wszystkie komorki.

## Kolejny etap

W Zadaniu 2 projekt zostanie rozszerzony o pipeline
przygotowania danych oraz modelowanie.
Dwa niezalezne zbiory beda obslugiwane
przez osobne galezie pipeline Kedro.
