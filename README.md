# Простой HTTP-сервер на Go

Этот проект представляет собой простой HTTP-сервер на Go с тремя основными эндпоинтами:
1. Эндпоинт /hello
2. Эндпоинт /user
3. Эндпоинт /health

---

## Установка и запуск

(Необходимы предустановленные Go и Git)

Клонировать репозиторий:

```
git clone https://github.com/Unpatches/helloapi
cd helloapi
```

Команда запуска сервера:

```
go run ./cmd/server
```

Также можно запустив файл helloapi.exe

------

## Структура проекта

helloapi/  
├── cmd/  
│      └── server/  
│              └── main.go  
├── go.mod  
├── go.sum
└── helloapi.exe

## Запросы, на которые отвечает сервер

```
curl http://localhost:8080/hello
```
- Возвращает текстовый ответ "Hello, world!"

- Content-Type: text/plain
```
curl http://localhost:8080/user
```
- Возвращает JSON с данными пользователя

- Генерирует уникальный UUID для каждого запроса

- Содержит фиксированное имя "Gopher"

- Content-Type: application/json
```
curl http://localhost:8080/health
```
- Возвращает статус здоровья сервера в формате JSON

- Включает текущее время в формате RFC3339

- Всегда возвращает статус "ok"

- Content-Type: application/json

------

## Запуск на другом порту (по умолчанию 8080)
Команда смены порта
```
$env:APP_PORT="8081"
go run ./cmd/server
```
В кавычках меняется порт
