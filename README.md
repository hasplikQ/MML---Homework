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

## Poznámka k datům a reprodukovatelnosti
Původní dataset z platformy Kaggle (`ks-projects-201801.csv`) obsahuje přes 300 000 záznamů a má velikost cca 58 MB. Z důvodu velikosti není tento zdrojový soubor fyzicky nahrán v repozitáři (v souladu s povolenou výjimkou v zadání HW2). 

Aby byla zaručena 100% reprodukovatelnost bez nutnosti manuálního stahování velkých souborů, **oba notebooky obsahují kód (využívající knihovnu `gdown`), který si při spuštění automaticky stáhne potřebný dataset** přímo z mého Google Drive. `benchmark.ipynb` je navíc napsán zcela nezávisle a provádí bleskovou reprodukci přípravy dat i splitu z prvního notebooku.

**Jak spustit kód (doporučeno např. v Google Colab):**
1. Spusťte `dataprocessing.ipynb`. Notebook si sám do paměti stáhne původní dataset, očistí jej od leakage proměnných, rozdělí chronologicky na sady a vytvoří preprocessing pravidla výhradně na trénovacích datech.
2. Následně spusťte `benchmark.ipynb`. Notebook si opět sám stáhne data, provede čistý split a natrénuje a vyhodnotí referenční modely na validační sadě.
