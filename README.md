# Docker-mirror

Конфигурация зеркалирования докерхаба с автоматическим выпуском сертификата https по http-challenge

Работает и напрямую
```
docker pull example.com/nginx:latest
```
И если указать в конфиге демона
```
{
    "registry-mirrors": ["https://example.com"]
}
```

Для изменения конфигурации registry можно воспользоваться документацией https://distribution.github.io/distribution/about/configuration/

### Запуск

1. Создать А запись в днс, указывающую на ip сервера, куда будет устанавливаться docker-mirror, указать ее в .env
2. Изменить acme email в `traefik.yml` (опционально)
3. Установить docker, docker-compose
5. `docker-compose up -d`
