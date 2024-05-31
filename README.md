# Docker-mirror

Конфигурация зеркалирования докерхаба с автоматическим выпуском сертификата https по http-challenge

Работает и напрямую
```
docker pull example.com/nginx:latest
```
И если указать в конфиге демона /etc/docker/daemon.json (нужно перезагрузить демон `service docker reload`)
```
{
    "registry-mirrors": ["https://example.com"]
}
```

Для изменения конфигурации registry можно воспользоваться документацией https://distribution.github.io/distribution/about/configuration/

### Запуск

1. Создать А запись в днс, указывающую на ip сервера, куда будет устанавливаться docker-mirror, указать ее в [.env](.env)
2. Изменить acme email в [traefik.yml](traefik.yml) (опционально)
3. Установить docker, docker-compose
5. `docker-compose up -d`
