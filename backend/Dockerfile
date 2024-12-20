# Используем официальный образ Python 3.9
FROM python:3.9

# Устанавливаем рабочую директорию внутри контейнера
WORKDIR /app

# Копируем файл зависимостей и устанавливаем их
COPY requirements.txt .
RUN pip install --upgrade pip
RUN pip install -r requirements.txt --no-cache-dir

# Копируем весь код проекта в контейнер
COPY . .

# Устанавливаем gunicorn для запуска приложения
RUN pip install gunicorn==20.1.0

# Запускаем сервер с помощью gunicorn
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "backend.wsgi"]

