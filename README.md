# API Testing: Postman + Newman + GitHub Actions

[![Postman Collection](https://github.com/alisher-sdet/backend-postman-demo/actions/workflows/ci_postman.yml/badge.svg)](https://github.com/alisher-sdet/backend-postman-demo/actions/workflows/ci_postman.yml)

> **Происхождение проекта.** Учебный проект. [Выполнен по курсу «название» (Udemy, автор) / Создан с помощью ИИ-ассистента.]
> **Что сделал я:** [составил коллекцию, написал проверки, настроил запуск в GitHub Actions, исправлял падения ...].
> **Чего здесь нет:** [негативных сценариев / схем ответов / переменных окружения / HTML-отчёта ...].

## Описание

Коллекция Postman, которая запускается через Newman в GitHub Actions при каждом `push`. Результаты запусков: [вкладка Actions](https://github.com/alisher-sdet/backend-postman-demo/actions/workflows/ci_postman.yml).

## Что проверяют тесты

- Тестируемый API: [название и адрес]
- Запросов в коллекции: [N], проверок (`pm.test`): [M]
- Что проверяется: [статус-коды, поля тела ответа, заголовки ...]

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

Каждый `push` запускает коллекцию через Newman; результат виден в разделе **Actions**. [Если в workflow есть шаг с JSON-отчётом и `upload-artifact`, добавьте: «JSON-отчёт доступен как артефакт запуска».]

---

## Summary (EN)

Learning project: a Postman collection run with Newman in GitHub Actions on every push. See the origin note above for what it is based on and what it does not cover.
