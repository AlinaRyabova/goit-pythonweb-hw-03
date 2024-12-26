# Використовуємо базовий образ Python
FROM python:3.10-slim

# Встановлення залежностей системи
RUN apt-get update && apt-get install -y \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

# Копіюємо файл з залежностями і встановлюємо Python-бібліотеки
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Встановлюємо робочу директорію
WORKDIR /app

# Копіюємо всі файли проекту до контейнера
COPY . .

# Переконуємося, що папка storage існує і доступна для запису
RUN mkdir -p /app/storage && chmod -R 777 /app/storage

# Встановлюємо команду за замовчуванням для запуску додатка
CMD ["python", "app.py"]
