# Restful Booker API — QA Test Suite

Набор для тестового задания по проверке REST API сервиса Restful Booker.

## Состав проекта

- `postman/Restful-Booker-API.postman_collection.json` — коллекция Postman с позитивными и негативными сценариями и проверками ответа.
- `postman/Restful-Booker.postman_environment.json` — окружение с переменными `baseUrl`, `token`, `bookingId` и снимком полей для проверки PATCH.
- `test-cases/Restful-Booker-Test-Cases.xlsx` — тест-кейсы и фактические результаты прогона.
- `bug-reports/Restful-Booker-Bug-Reports.xlsx` — два воспроизведённых дефекта.

## Как запустить

1. Импортировать JSON-файлы из папки `postman` в Postman.
2. Выбрать окружение **Restful Booker**.
3. Запустить `AUTH-01 — Valid credentials`, затем `BOOKING-01 — Valid booking`.
4. Выполнять связанные запросы коллекции последовательно, особенно `PUT`, `PATCH`, `DELETE` и проверку после удаления.
5. Два последних негативных сценария `BOOKING-02` и `BOOKING-03` отражают дефекты, найденные при выполнении задания. До исправления API соответствующие проверки ожидаемо падают.

## Известные дефекты

- **BR-01:** `POST /booking` возвращает `500 Internal Server Error`, если отсутствует `firstname`, вместо контролируемого ответа валидации.
- **BR-02:** `POST /booking` принимает строку в `totalprice` (например, `"abc"`), создаёт бронирование и возвращает `totalprice: null`.

## Важные замечания

- Это учебный демо-сервис. Его тестовые данные могут периодически сбрасываться; используйте актуальный `bookingId` и не делайте большие паузы между зависимыми запросами.
- `PUT`, `PATCH` и `DELETE` используют `Cookie: token={{token}}`.
- Набор основан на наблюдениях при ручном прогоне 23–25 октября 2026 года. Результаты на стенде могут меняться.

## Документация API

https://restful-booker.herokuapp.com/apidoc/index.html
