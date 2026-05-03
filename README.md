# Predikce úspěchu Kickstarter kampaní (MML1 - HW2)

Tento repozitář obsahuje vypracování 2. domácího úkolu (Data processing, split dat a benchmark) pro kurz Machine Learning.

## Cíl projektu
Cílem je vytvořit model pro binární klasifikaci, který odhadne šanci na úspěch crowdfundingové kampaně na Kickstarteru výhradně na základě dat dostupných před jejím spuštěním (pre-launch atributy). Výstupem je kalibrovaná pravděpodobnost úspěchu, která má tvůrcům pomoci optimalizovat parametry kampaně a minimalizovat riziko finanční ztráty způsobené špatným nastavením.

## Struktura repozitáře
* `README.md` - Tento soubor s popisem projektu.
* `dataprocessing.ipynb` - Notebook obsahující EDA, leakage audit, chronologický (time-based) split a preprocessing pipeline.
* `dataprocessing.html` - Export notebooku pro prohlížení bez nutnosti spouštět kód.
* `benchmark.ipynb` - Notebook s naivním a ML benchmarkem (logistická regrese), vyhodnocený na validační sadě (F1-score, Brier score).
* `benchmark.html` - Export benchmark notebooku.
* `data/` - Složka obsahující výsledné datové sady (`train.csv`, `validation.csv`, `test.csv`).

## Poznámka k datům a reprodukovatelnosti
Původní dataset z platformy Kaggle (`ks-projects-201801.csv`) obsahuje přes 300 000 záznamů a má velikost cca 58 MB. Z důvodu velikosti není tento zdrojový soubor přímo nahrán v repozitáři (dle povolené výjimky v zadání HW2). 

Zpracované a rozdělené datové sady (train, validation, test) jsou však k dispozici ve složce `data/`.

**Jak spustit kód:**
1. Pro úplnou reprodukci stáhněte původní dataset z Kaggle a vložte jej do hlavní složky.
2. Spusťte `dataprocessing.ipynb`. Tento notebook data očistí od průběhových (leakage) proměnných, rozdělí je chronologicky a vytvoří preprocesingová pravidla výhradně na trénovací sadě.
3. Následně spusťte `benchmark.ipynb`, který na těchto datech natrénuje a vyhodnotí referenční modely.
