# Використовуємо офіційний образ Python 3.10
FROM python:3.10

# Встановлюємо робочу директорію
WORKDIR /app

# Копіюємо файл залежностей
COPY requirements.txt .

# Встановлюємо залежності, включаючи gunicorn та uvicorn
RUN pip install --no-cache-dir -r requirements.txt

# Копіюємо весь код застосунку в робочу директорію
COPY . .

# Команда для запуску застосунку Gunicorn
CMD ["gunicorn", "main:app", "--workers", "4", "--worker-class", "uvicorn.workers.UvicornWorker", "--bind", "0.0.0.0:8000"]