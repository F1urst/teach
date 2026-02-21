# !/bin/bash

# создаем папку
mkdir -p /opt/app

# создаем файл
touch /opt/app/log.txt

# генерирует случайную стору до 20 символов
# печатные символы
while true; do
    RANDOM_STRING=$(cat /dev/urandom | tr -dc 'a-zA-Z0-9' | fold -w $((RANDOM % 20 + 1)) | head -n 1)

# записывает с новой строки
    echo "[$TIMESTAMP] $RANDOM_STRING" >> /opt/app/log.txt

# ждем 17сек
    sleep 17
done
