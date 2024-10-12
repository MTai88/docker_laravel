## Laravel Docker Compose workflow
Докер окружение для локальной разработки на фреймворке Laravel. Включены контейнеры Postgres, MailHog, Adminer, Redis

## Установка

### Конфигурация файла настроек

Скопируйте файл `.env_template` в `.env`

```
cp -f .env_template .env
```

Вы можете изменить настройки ```.env``` файла:

```
# Имя проекта в docker
COMPOSE_PROJECT_NAME=laravel

# Настройки пользователя Postgres.
POSTGRES_DB=laravel
POSTGRES_USER=laravel
POSTGRES_PASSWORD=123

# Путь к корню портала laravel
SITE_PATH=../www
```

## Запуск и остановка контейнеров
### Запуск
```
docker compose up -d
```

### Остановка
```
docker compose down
```

### В случае изменения конфигов php, nginx нужно выполнить команду
```
docker compose build
```

## Настройки laravel ```.env```
- Пример настроек бд 
```
DB_CONNECTION=pgsql
DB_HOST=postgres
DB_PORT=5432
DB_DATABASE=laravel
DB_USERNAME=laravel
DB_PASSWORD=123
```
- Настройки Redis
```
REDIS_CLIENT=phpredis
REDIS_HOST=redis
REDIS_PASSWORD=null
REDIS_PORT=6379
```
- Отправка писем на MailHog
```
MAIL_MAILER=smtp
MAIL_HOST=mailhog
MAIL_PORT=1025
```
- MailHog доступен по адресу http://localhost:8025/
- Adminer доступен по адресу http://localhost:8080/
