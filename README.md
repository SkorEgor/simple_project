# Simple Project

Простой пример проекта на Python с использованием Poetry.

## Установка и запуск через Poetry

### 1. Склонируйте репозиторий
```bash
git clone https://github.com/SkorEgor/simple_project.git
cd simple_project
```

### 2. Установите зависимости
Убедись, что Poetry установлен:
```bash
pip install poetry
```
Затем выполни:
```bash
poetry install
```
Poetry создаст виртуальное окружение и установит проект как пакет.

### 3. Запустите проект
```bash
poetry run start
```

### Ожидаемый вывод
```
Привет, Мир!
```

## Установка и запуск через pip

### Вариант 1: Установка из локальной копии

#### 1. Склонируйте репозиторий
```bash
git clone https://github.com/SkorEgor/simple_project.git
cd simple_project
```

#### 2. Создайте виртуальное окружение (опционально)
```bash
python -m venv venv
```
Активируйте его:
- На Windows:
```bash
venv\Scripts\activate
```
- На Linux/Mac:
```bash
source venv/bin/activate
```

#### 3. Установите проект
```bash
pip install .
```
Точка (`.`) указывает на текущую директорию, где находится `pyproject.toml`.

#### 4. Запустите проект
В Windows `start` может конфликтовать с системной командой. Используйте:
```bash
python -m simple_project.main
```
Или переименуйте скрипт в `pyproject.toml` (см. примечание ниже).

### Вариант 2: Установка напрямую из GitHub

#### 1. Установите проект из репозитория
```bash
python -m pip install git+https://github.com/SkorEgor/simple_project.git
```
Это установит проект напрямую из GitHub в активное окружение (глобальное или виртуальное).

#### 2. Запустите проект
```bash
python -m simple_project.main
```

### Ожидаемый вывод
```
Привет, Мир!
```

### Примечание
Команда `start`, указанная в `[tool.poetry.scripts]`, может конфликтовать с системной командой `start` в Windows. Чтобы использовать `start` напрямую:
1. Открой `pyproject.toml`.
2. Измени `[tool.poetry.scripts]` на, например:
   ```toml
   [tool.poetry.scripts]
   run-simple = "simple_project.main:main"
   ```
3. Установи проект заново (`poetry install` или `pip install .`).
4. Запускай как `run-simple` вместо `start`.
\\