# Используем официальный образ Node.js 18
FROM node:18

# Устанавливаем рабочую директорию внутри контейнера
WORKDIR /app

# Копируем файлы зависимостей и устанавливаем их
COPY package.json package-lock.json ./
RUN npm install

# Копируем весь код проекта в контейнер и собираем приложение
COPY . .
RUN npm run build

# Устанавливаем http-server для раздачи статических файлов
RUN npm install -g http-server

# Запускаем сервер для раздачи статических файлов
CMD ["http-server", "build", "-p", "8000"]

