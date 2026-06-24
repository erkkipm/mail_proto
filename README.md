# mail_proto

Proto-контракты почтового микросервиса [Mail](https://github.com/erkkipm/Mail) (gRPC, `mail.v1`).

## Сервисы

| Сервис | Скоуп ключа | Назначение |
|---|---|---|
| `SendService` | `send` | Отправка транзакционных писем из бэкендов сайтов |
| `MailboxService` | `read` | Чтение почты из админки бэк-офиса |
| `AdminService` | `admin` | Домены, DKIM, ящики, очередь, подавления, статистика |

Аутентификация — метаданные `x-api-key`. Транспорт — TLS (опционально mTLS).

## Генерация кода

```bash
make install   # protoc-gen-go, protoc-gen-go-grpc
make gen       # генерирует gen/go/mail/v1/
```

## Версионирование

Git-теги (`v0.1.0`, ...). Подключение в потребителях:

```bash
go get github.com/erkkipm/mail_proto@v0.1.0
```

Для локальной разработки в `go.mod` потребителя:

```
replace github.com/erkkipm/mail_proto => ../mail_proto
```
