# API Testing: Postman + Newman + GitHub Actions

[![Postman Collection](https://github.com/alisher-sdet/backend-postman-demo/actions/workflows/ci_postman.yml/badge.svg)](https://github.com/alisher-sdet/backend-postman-demo/actions/workflows/ci_postman.yml)

> **Происхождение проекта.** Учебный проект. При работе использовался ИИ-ассистент.
> **Что сделал я:** составил коллекцию, настроил запуск через Newman в GitHub Actions.
> **Чего здесь нет:** проверки значений полей и схемы ответа, методов PUT/PATCH/DELETE, негативных сценариев.

## Описание

Минимальная коллекция Postman, которая запускается через Newman в GitHub Actions при каждом `push`. Результаты запусков: [вкладка Actions](https://github.com/alisher-sdet/backend-postman-demo/actions/workflows/ci_postman.yml).

## Что проверяют тесты

- **Тестируемый API:** [JSONPlaceholder](https://jsonplaceholder.typicode.com) — бесплатный тестовый REST API, без авторизации. Он имитирует запись данных: POST возвращает ответ, но ничего не сохраняет, поэтому тесты проверяют контракт ответа, а не состояние данных.
- **Запросов в коллекции:** 2, проверок (`pm.test`): 4.

| Запрос | Что проверяется |
| --- | --- |
| `GET /posts` | статус 200; тело ответа — массив |
| `POST /posts` (тело: `title`, `body`, `userId`) | статус 201; в ответе есть поле `id` |

**Чего здесь нет:** проверки значений полей и схемы ответа, запросов `PUT`/`PATCH`/`DELETE`, получения записи по id, негативных сценариев (несуществующий id, пустое тело), переменных окружения, проверки времени ответа.

## Запуск локально

```bash
npm install -g newman
newman run TestAPICollection.json
```

## Стек

| Инструмент | Назначение |
| --- | --- |
| Postman | Проектирование запросов и проверок |
| Newman | Запуск коллекции из командной строки |
| GitHub Actions | Автоматический запуск при каждом push |

## Автоматический запуск

Каждый `push` запускает коллекцию через Newman; результат виден в разделе **Actions**. Newman-отчёт доступен как артефакт запуска.

---

## Summary (EN)

Learning project: a Postman collection run with Newman in GitHub Actions on every push. See the origin note above for what it is based on and what it does not cover.
