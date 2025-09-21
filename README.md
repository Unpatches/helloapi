# Простой HTTP-сервер на Go

Этот проект представляет собой простой HTTP-сервер на Go с тремя основными эндпоинтами:
1. Эндпоинт /hello
2. Эндпоинт /user
3. Эндпоинт /health

Проект демонстрирует базовые принципы создания REST API на Go с обработкой различных типов контента и использованием middleware-подхода

---

## Установка и запуск
Версия Go

![photo_5364233910562714441_x](https://github.com/user-attachments/assets/b41e11b4-0d56-436b-82e6-4ce3c5e6027b)

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

```plaintext
helloapi/                # Корень проекта
├── cmd/                 # Основные исполняемые файлы
│   └── server/          # Сервер приложения
│       └── main.go      # Точка входа
├── go.mod               # Файл зависимостей Go
├── go.sum               # Контрольные суммы зависимостей
└── helloapi.exe         # Скомпилированный исполняемый файл (Windows)
```

## Запросы, на которые отвечает сервер

```
curl http://localhost:8080/hello
```
- Возвращает текстовый ответ "Hello, world!"

- Content-Type: text/plain
![photo_5364233910562714442_y](https://github.com/user-attachments/assets/b2b28eaf-19b8-46f1-9e23-fbe171f95e8b)

```
curl http://localhost:8080/user
```
- Возвращает JSON с данными пользователя

- Генерирует уникальный UUID для каждого запроса

- Содержит фиксированное имя "Gopher"

- Content-Type: application/json
![photo_5364233910562714443_y](https://github.com/user-attachments/assets/1331ef14-21dd-4316-8d9a-84165a19c7c3)

```
curl http://localhost:8080/health
```
- Возвращает статус здоровья сервера в формате JSON

- Включает текущее время в формате RFC3339

- Всегда возвращает статус "ok"

- Content-Type: application/json
![photo_5364233910562714444_y](https://github.com/user-attachments/assets/36cc0a1e-d0e4-4a2c-9c1a-30261e141470)

------

## Запуск на другом порту (по умолчанию 8080)
Команда смены порта
```
$env:APP_PORT="8081"
go run ./cmd/server
```
В кавычках меняется порт
