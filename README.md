# DevOps
## Практика №1. Изучение **Markdown**
### Вариант 2. Проект: Docker-контейнер для Redis
#### 1. Описание и назначение проекта:
**Docker-контейнер для Redis** - быстрое развертывание Redis-сервера в изолированной среде.
Контейнер основан на Alpine Linux для минимального размера и максимальной производительности.

Основное назначение:
- Кэширование данных веб-приложений
- Хранение сессий пользователей
- Очереди сообщений для фоновых задач
- Временное хранилище для высоконагруженных приложений

#### 2. Таблица поддерживаемых аргументов образа и их описаний:
| Переменная окружения| Обязательность | Описание |
| --------------------| -------------- |----------|
|REDIS_PORT|Необязательно|Порт для подключения к Redis|
|REDIS_PASSWORD|Обязательно|Пароль для аутентификации|
|REDIS_DATABASE|Необязательно|Кол-во доступных БД|
|REDIS_APENDONLY|Необязательно|Вкл. Persistence-режима|
|REDIS_MAXMEMORY|Необязательно|Максимальный объем памяти|
|REDIS_BIND|Необязательно|IP-адрес для привязки|
|REDIS_PROTECTED_MOD|Необязательно|Защищенный режим|

#### 3. Пример команды docker run в блоке кода
'''docker 
  docker run -d \
  --name my-redis-container \
  -p 6379:6379 \ 
REDIS_PASSWORD="123215" \ 
  -e REDIS_PORT=6379 \
  -e REDIS_DATABASE=8 \
  -e REDIS_APENDONLY=yes \
  -e REDIS_MAXMEMORY=256mb \
  -e REDIS_PROTECTED_MOD=yes \ 
  -v redis_storage:/data \
  --restart unless=stopped \
  mycompany/redis-cust:1.0.0
'''
#### 4. Инструкции по настройке через переменные окружения в списках.
1. Настройка аутентификации
> Установите сложный пароль через REDIS_PASSWORD. Пример: REDIS_PASSWORD=123
2. Конфигурация сети
> Измените порт через REDIS_PORT для безопасности. Пример: REDIS_PORT=80

![Спасибо за внимание!]>(https://www.google.com/url?sa=i&url=https%3A%2F%2Fshrek.fandom.com%2Fru%2Fwiki%2F%25D0%25A8%25D1%2580%25D0%25B5%25D0%25BA_%2528%25D0%25BF%25D0%25B5%25D1%2580%25D1%2581%25D0%25BE%25D0%25BD%25D0%25B0%25D0%25B6%2529&psig=AOvVaw2e0vadHhnRyFCbQC6JR3YR&ust=1763272760302000&source=images&cd=vfe&opi=89978449&ved=0CBEQjRxqFwoTCLjptLqy85ADFQAAAAAdAAAAABAE)
