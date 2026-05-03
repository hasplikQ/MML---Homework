# Predikce úspěchu kampaní na Kickstarteru (MML1 - HW2)

Tento repozitář obsahuje vypracování 2. domácího úkolu (Data processing, split dat a benchmark) pro kurz Machine Learning. 

## Cíl projektu
Cílem je vytvořit model pro binární klasifikaci, který před spuštěním crowdfundingové kampaně na Kickstarteru odhadne její šanci na úspěch. Tím má pomoci tvůrcům optimalizovat parametry kampaně a snížit finanční rizika.

## Struktura repozitáře
* `README.md` - Tento soubor s popisem projektu.
* `dataprocessing.ipynb` - Notebook obsahující EDA, leakage audit, time-based split a preprocessing pipeline.
* `dataprocessing.html` - Export notebooku pro snadné prohlížení.
* `benchmark.ipynb` - Notebook s vytvořením naivního a ML benchmarku (logistická regrese) vyhodnocených na validační sadě.
* `benchmark.html` - Export benchmark notebooku.
* `data/` - Složka obsahující výsledné datasety (`train.csv`, `validation.csv`, `test.csv`).

## Poznámka k datům
Původní dataset z platformy Kaggle ("Kickstarter Projects") obsahuje statisíce záznamů a je příliš velký (cca 58 MB) pro standardní nahrávání do repozitáře. Podle pokynů k HW2 proto repozitář obsahuje pouze zmenšený vzorek `source reduced.csv`. V notebooku `dataprocessing.ipynb` je ukázáno, jak se z tohoto vzorku generují finální sady (train, validation, test), které jsou uloženy ve složce `data/`.
