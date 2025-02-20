# Описание проекта

## Описание
Этот проект представляет собой комплексное решение для обработки, анализа данных и обучения моделей машинного обучения на основе клиентских данных, таких как взаимодействие с маркетинговыми рассылками и данные о покупках. Проект построен с использованием Python и библиотек для анализа данных, таких как `pandas`, `numpy`, `matplotlib`, а также библиотек для машинного обучения, таких как `sklearn`, `CatBoost`, `LightGBM` и `Optuna`.

## Основные этапы
1. **Предобработка данных**:
    - Чистка данных от дубликатов и пропусков.
    - Преобразование типов данных.
    - Создание новых признаков из имеющихся данных (например, период активности, сумма покупок, количество уникальных категорий).

2. **Анализ данных**:
    - Вычисление корреляций между признаками.
    - Удаление признаков с высокой корреляцией для уменьшения мультиколлинеарности.

3. **Создание признаков**:
    - Объединение данных о покупках и взаимодействиях с рассылками.
    - Добавление новых признаков, таких как количество сообщений, сумма покупок, медианная цена и другие.

4. **Обучение моделей**:
    - Настройка и обучение различных моделей, включая `Logistic Regression`, `KNN`, `Decision Tree`, `CatBoost`, и `LightGBM`.
    - Оптимизация гиперпараметров с использованием `Optuna`.
    - Оценка качества моделей по метрике ROC-AUC.

## Использование

### Требования
- Python 3.10+
- Установленные библиотеки:
    - `pandas`
    - `numpy`
    - `matplotlib`
    - `seaborn`
    - `scikit-learn`
    - `catboost`
    - `lightgbm`
    - `optuna`

Для установки необходимых библиотек выполните:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn catboost lightgbm optuna
```

### Инструкция

1. **Подготовка данных**:
    - Разместите файлы данных (`apparel-messages.csv`, `apparel-purchases.csv`, `apparel-target_binary.csv`) в директории проекта.
    - Убедитесь, что данные соответствуют ожидаемому формату.

2. **Запуск анализа и предобработки**:
    - Запустите ноутбук `Untitled2.ipynb` для выполнения всех этапов анализа данных и обучения моделей.

3. **Настройка моделей**:
    - При необходимости измените параметры в блоке определения моделей.

4. **Обучение и оценка**:
    - После выполнения ячеек ноутбука будет выведена информация о наилучших моделях и их параметрах.

5. **Результаты**:
    - Вывод ROC-AUC для каждой модели.
    - Рекомендации по дальнейшему улучшению качества моделей (при необходимости).

### Структура данных

#### Файл `apparel-messages.csv`
- `bulk_campaign_id`: ID кампании.
- `client_id`: ID клиента.
- `message_id`: ID сообщения.
- `event`: Тип события (например, open, click).
- `channel`: Канал рассылки (email, sms).
- `date`: Дата события.
- `created_at`: Дата и время создания записи.

#### Файл `apparel-purchases.csv`
- `client_id`: ID клиента.
- `quantity`: Количество товаров.
- `price`: Цена товара.
- `category_ids`: Категории товара.
- `date`: Дата покупки.
- `message_id`: ID сообщения, связанного с покупкой.

#### Файл `apparel-target_binary.csv`
- `client_id`: ID клиента.
- `target`: Целевой признак (1 - активный клиент, 0 - неактивный клиент).


