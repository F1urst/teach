#!/bin/bash

# скрипт проверки доступности 
# использование: $0 <URL>

[ $# -eq 0 ] && { echo "использование: $0 <URL>"; exit 1; }

URL=$1
HOST=$(echo "$URL" | sed -e 's|^[^/]*//||' -e 's|[/:?#].*$||')

echo "проверка: $URL"

# проверка сетевой доступности

if ! ping -c 2 -W 2 "$HOST" >/dev/null 2>&1 && \
   ! timeout 2 bash -c ">/dev/tcp/$HOST/80" 2>/dev/null; then
    echo "ошибка: сетевая недоступность $HOST"
    exit 1
fi

# проверка HTTP доступности

if command -v curl >/dev/null; then
    HTTP_CODE=$(curl -s -o /dev/null -w "%{http_code}" --max-time 5 "$URL" 2>/dev/null || echo "000")
    if [[ $HTTP_CODE =~ ^[23]..$ ]]; then
        echo "успех: HTTP $HTTP_CODE"
        exit 0
    else
        echo "ошибка: HTTP $HTTP_CODE"
        exit 1
    fi
elif command -v wget >/dev/null; then
    if wget --spider --timeout=5 --tries=1 --quiet "$URL" 2>/dev/null; then
        echo "успех: Ресурс доступен"
        exit 0
    else
        echo "ошибка: Ресурс недоступен"
        exit 1
    fi
else
    echo "ошибка: установите curl или wget"
    exit 1

fi
