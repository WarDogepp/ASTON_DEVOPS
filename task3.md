## Создаем папку и через -p если нужно промежуточные

mkdir -p /opt/app

## Создание log.txt

touch /opt/app/log.txt

## Бесконечный цикл с генерацией строки , запись в log.txt и слип на 17 секунд


while true; do

    RANDOM_STRING=$(cat /dev/urandom | tr -dc 'a-zA-Z0-9' | head -c 20)

    echo "$RANDOM_STRING" >> /opt/app/log.txt

    sleep 17


done




## Сам скрипт 

#!/bin/bash


mkdir -p /opt/app

touch /opt/app/log.txt


while true; do

    RANDOM_STRING=$(cat /dev/urandom | tr -dc 'a-zA-Z0-9' | head -c 20)

    echo "$RANDOM_STRING" >> /opt/app/log.txt

    sleep 17


done
