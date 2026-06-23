# 🌌 Stellar Classification — Kaggle Playground S6E6

Классификация космических объектов (**GALAXY / STAR / QSO**) по фотометрическим данным SDSS.

[![Kaggle](https://img.shields.io/badge/Kaggle-PS_S6E6-20BEFF?logo=kaggle)](https://www.kaggle.com/competitions/playground-series-s6e6)
![Python](https://img.shields.io/badge/Python-3.11-3776AB?logo=python&logoColor=white)
![LightGBM](https://img.shields.io/badge/LightGBM-gradient_boosting-success)

## 📋 О проекте

Соревнование по мультиклассовой классификации на табличных данных.
**Метрика:** Balanced Accuracy.

| Признак | Описание |
|---------|----------|
| `u, g, r, i, z` | Яркость в 5 спектральных диапазонах SDSS |
| `redshift` | Красное смещение — ключевая разделяющая фича |
| `spectral_type`, `galaxy_population` | Категориальные характеристики |

## 📁 Структура

```
stellar_class/
├── notebooks/
│   ├── 01_EDA.ipynb          # Разведочный анализ
│   ├── 02_baseline.ipynb     # Baseline LightGBM
│   ├── 03_features_v2.ipynb  # Расширенный feature engineering
│   └── 04_optuna.ipynb       # Автоподбор гиперпараметров
├── data/                     # Данные (не в репозитории)
└── submissions/              # Файлы предсказаний
```

## 🔬 Подход

1. **EDA** — анализ распределений, корреляций, разделимости классов
2. **Feature Engineering** — цветовые индексы (`u-g`, `g-r`...), лог-трансформации, interaction terms
3. **Моделирование** — LightGBM + Stratified K-Fold CV
4. **Тюнинг** — Optuna (байесовская оптимизация)

## 📊 Результаты

| Версия | CV Score | Описание |
|--------|----------|----------|
| v1 | 0.93721 | Baseline LightGBM |
| v2 | 0.93755 | Расширенный feature engineering |
| v3 | *в работе* | Optuna tuning |

## 🚀 Запуск

```bash
pip install -r requirements.txt
jupyter notebook notebooks/01_EDA.ipynb
```

## 🛠 Стек

`Python` · `pandas` · `LightGBM` · `scikit-learn` · `Optuna` · `matplotlib`

---
*Учебный проект по data science. Цель — изучение пайплайна Kaggle-соревнований.*
