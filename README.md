# Оценка риска ДТП для каршеринговых сервисов

Система машинного обучения для оценки риска ДТП в реальном времени для каршеринговых сервисов.  
Цель проекта — разработка модели, которая предсказывает вероятность ДТП на маршруте и предлагает альтернативные пути при высоком риске.

## 🎯 Цель проекта

- Предсказывать вероятность ДТП с учетом виновности автомобилей и серьезности повреждений
- Анализировать ключевые факторы, влияющие на аварии
- Дать рекомендации по созданию системы оценки риска и необходимому оборудованию

## 💡 Использованные технологии

- Python 3.x
- pandas, numpy, matplotlib, seaborn
- scikit-learn, catboost, torch, torchmetrics
- psycopg2, phik
- StandardScaler, OneHotEncoder, OrdinalEncoder, SimpleImputer
- Streamlit (для демо)
- Jupyter Notebook

## 🧪 Как запустить проект

```bash
git clone https://github.com/kagor4/Accident-Risk-Prediction-System.git
cd Accident-Risk-Prediction-System
pip install -r requirements.txt
```

Затем откройте и запустите файл `Accident Risk Prediction System.py` или ноутбук с аналогичным кодом в Jupyter. Убедитесь, что у вас есть доступ к базе данных PostgreSQL с таблицами `collisions`, `parties`, `vehicles`, и `case_ids`.

## 📊 Описание данных

Проект использует данные из базы PostgreSQL:
- `collisions`: информация о ДТП (место, время, погода, повреждения)
- `parties`: участники ДТП (виновность, трезвость, тип участника)
- `vehicles`: данные о транспортных средствах (тип, возраст, трансмиссия)
- `case_ids`: идентификаторы случаев

Фильтрация данных:
- Только автомобили как виновники (`at_fault = 1`)
- ДТП 2012 года
- Повреждения, кроме царапин

Ключевые признаки:
- `distance` — расстояние до главной дороги
- `vehicle_type` — тип транспортного средства
- `vehicle_age` — возраст автомобиля
- `weather_1` — погодные условия
- `location_type` — тип местоположения

## 🔍 Краткие результаты

- Лучшая модель: Нейронная сеть
- Метрика: F1 = 0.71 (обучающая выборка), 0.674 (тестовая выборка)
- Основные факторы риска:
  - Расстояние до главной дороги (`distance`)
  - Тип транспортного средства (`vehicle_type`)
- Основные выводы:
  - Ясная погода увеличивает частоту ДТП из-за интенсивного движения
  - Старые легковые автомобили чаще попадают в аварии
- Рекомендации:
  - Добавить данные о погоде и дорожных условиях в реальном времени
  - Установить датчики (камеры, GPS) для мониторинга маршрута
  - Использовать ансамблевые методы для повышения точности
  - Разработать Streamlit-приложение для демонстрации системы

## 📁 Структура проекта

```
📦 Accident-Risk-Prediction-System/
├── Accident Risk Prediction System.py  # анализ и обучение модели
├── requirements.txt                    # зависимости
└── README.md                           # описание проекта
```

## ✅ TODO

- Интеграция данных о погоде и трафике в реальном времени
- Разработка Streamlit-приложения для визуализации рисков
- Тестирование ансамблевых методов (XGBoost, LightGBM)
- Улучшение обработки аномалий в данных

## © Автор

Автор: [kagor4](https://github.com/kagor4)
```
