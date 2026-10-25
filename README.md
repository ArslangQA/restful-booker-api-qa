# Restful Booker API — QA Project

## О проекте

Учебный проект по тестированию REST API сервиса Restful Booker. Включает тест-кейсы, Postman-коллекцию и баг-репорты.

## Содержание

- [Тест-кейсы](restful_booker_qa/test-cases/Restful-Booker-Test-Cases.xlsx)
- [Баг-репорты](restful_booker_qa/bug-reports/Restful-Booker-Bug-Reports.xlsx)
- [Postman Collection](restful_booker_qa/postman/Restful-Booker-API.postman_collection.json)
- [Postman Environment](restful_booker_qa/postman/Restful-Booker.postman_environment.json)
- [Подробное описание проекта](restful_booker_qa/README.md)

## Покрытие

- Авторизация: `POST /auth`
- Создание бронирования: `POST /booking`
- Поиск бронирований: `GET /booking`
- Получение бронирования: `GET /booking/:id`
- Полное обновление: `PUT /booking/:id`
- Частичное обновление: `PATCH /booking/:id`
- Удаление: `DELETE /booking/:id`
- Проверка доступности сервиса: `GET /ping`

## Найденные дефекты

**BR-01.** При создании бронирования без `firstname` API возвращает `500 Internal Server Error`.

**BR-02.** API принимает строковое значение `totalprice: "abc"`, создаёт бронирование и возвращает `totalprice: null`.

## Инструменты

- Postman
- REST API
- JSON
- Позитивное и негативное тестирование
