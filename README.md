# simple-REST-services

Документация REST API для проекта "Cat Service"
Автор: Амин Асмаров
Версия API: v1.0
Технологии:

Java 17

Spring Boot 3.x

Jackson (JSON-сериализация)

📌 Обзор API
Простое REST API для работы с котами. Позволяет получать информацию о котах в формате JSON.

Базовый URL:

text
http://ваш-сервер:8080/api/
🔧 Доступные эндпоинты
1. Проверка работоспособности API
Запрос:

http
GET /main
Ответ:

plaintext
Hello World
Пример вызова:

bash
curl -X GET http://localhost:8080/api/main
2. Получение стандартного кота
Запрос:

http
GET /cat
Ответ (JSON):

json
{
  "name": "Barsik",
  "age": 5,
  "color": "orange",
  "owner": "Asmar"
}
Пример вызова:

bash
curl -X GET http://localhost:8080/api/cat
Примечание:

Если произошла ошибка сериализации, возвращается null, а в лог выводится сообщение.

3. Создание кастомного кота
Запрос:

http
POST /special?name={имя_кота}
Параметры:

Параметр	Тип	Обязательный	Описание
name	String	Да	Имя нового кота.
Ответ (JSON):

json
{
  "name": "Ваше_имя",
  "age": 5,
  "color": "orange",
  "owner": "Asmar"
}
Пример вызова:

bash
curl -X POST "http://localhost:8080/api/special?name=Murzik"
Примечание:

Если имя не передано, Spring вернёт 400 Bad Request.

В случае ошибки сериализации возвращается null.
