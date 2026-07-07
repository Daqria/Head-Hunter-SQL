# Анализ вакансий HeadHunter (SQL)

Учебный проект по SQL и анализу данных: исследование базы вакансий HeadHunter в PostgreSQL с помощью SQL-запросов и Jupyter Notebook.

## Описание

В проекте анализируются данные о вакансиях, работодателях, регионах и сферах деятельности. Работа выполняется в ноутбуке [`HH_PROJECT.ipynb`](HH_PROJECT.ipynb) — через SQL-запросы к удалённой базе PostgreSQL, результаты выводятся в виде таблиц pandas.


## Структура базы данных

Основные таблицы:

| Таблица | Описание |
|---------|----------|
| `vacancies` | Вакансии: название, навыки, график, опыт, занятость, зарплата, регион, работодатель |
| `employers` | Работодатели: название, регион |
| `areas` | Регионы |
| `industries` | Сферы деятельности |
| `employers_industries` | Связь работодателей и сфер (many-to-many) |

## Стек

- Python 3.10+
- PostgreSQL
- pandas — вывод результатов запросов
- psycopg2 — подключение к БД
- Jupyter Notebook — среда выполнения

## Быстрый старт

### 1. Клонировать репозиторий

```bash
git clone <url-репозитория>
cd "Head Hunter SQL"
```

### 2. Создать виртуальное окружение и установить зависимости

```bash
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

### 3. Настроить подключение к БД

Создайте файл `.env` в корне проекта:

```env
DBNAME=your_database
USER=your_user
HOST=your_host
PASSWORD=your_password
PORT=5432
```

> Файл `.env` добавлен в `.gitignore` — не коммитьте учётные данные.

### 4. Запустить ноутбук

```bash
jupyter notebook HH_PROJECT.ipynb
```

Выполните ячейки сверху вниз. Подключение к базе и вспомогательные функции (`connect()`, `show_df()`) определены в начале ноутбука.

## Структура проекта

```
Head Hunter SQL/
├── HH_PROJECT.ipynb   # Основной ноутбук с SQL-запросами и выводами
├── requirements.txt   # Зависимости Python
├── .env               # Параметры подключения к БД (не в git)
└── README.md
```

## Автор

Учебный проект в рамках курса по анализу данных (Skillfactory).
