# DummyAPI

## Оглавление
1. [Описание проекта](#Описание-проекта)
    1. [POST](#USER)
        1. [GET /user (Get List)](#GET-user-Get-List)
2. [Майнд-карта](#Майнд-карта)


## Описание проекта
https://dummyapi.io/ представляет собой сервис для тестирования АПИ. Для выполнения запросов необходим app-id, который генерируется автоматически при регистрации на сервисе. В качестве тестирования были взят объект **USER**.

### USER
____
#### GET /user (Get List)
Возвращает список пользователей отсортировнных по дате регистрации. 
- доступен query params для вывода определенной страницы.
- доступен query params для отображения числа пользователей на странице.

**Response Body**:

**List**
```javascript
{
  data: Array(Model)
  total: number(total items in DB)
  page: number(current page)
  limit: number(number of items on page)
}
```
**User Preview**
```javascript
{
  id: string(autogenerated)
  title: string("mr", "ms", "mrs", "miss", "dr", "")
  firstName: string(length: 2-50)
  lastName: string(length: 2-50)
  picture: string(url)
}
```
____
#### POST /user/create (Create User)
Создает нового пользователя. Возвращает данные о пользователе.

**Request Body**:

**User Full**
```javascript
{
  title: string("mr", "ms", "mrs", "miss", "dr", "")
  firstName: string(length: 2-50)
  lastName: string(length: 2-50)
  gender: string("male", "female", "other", "")
  email: string(email)
  dateOfBirth: string(ISO Date - value: 1/1/1900 - now)
  phone: string(phone number - any format)
  picture: string(url)
  location: object(Location)
}
```
**Location**
```javascript
{
  street: string(length: 5-100)
  city: string(length: 2-30)
  state: string(length: 2-30)
  country: string(length: 2-30)
  timezone: string(Valid timezone value ex. +7:00, -1:00)
}
```
**Response Body**:

**User Full**
```javascript
{
  id: string(autogenerated)
  title: string("mr", "ms", "mrs", "miss", "dr", "")
  firstName: string(length: 2-50)
  lastName: string(length: 2-50)
  gender: string("male", "female", "other", "")
  email: string(email)
  dateOfBirth: string(ISO Date - value: 1/1/1900 - now)
  registerDate: string(autogenerated)
  phone: string(phone number - any format)
  picture: string(url)
  location: object(Location)
}
```



## Майнд-карта
Данная МК представляет собой набор тестов для тестирования объекта **POST**. Подробная проверка расписана для **Get List** и **Create Post**
![Alt-текст](https://i.imgur.com/k4wusSC.png "МК")

Также майнд-карту можно [скачать](https://github.com/RetMiC/DummyAPI/blob/main/POST%20(2).xmind)

## Тест-кейсы
Также были оформлены тест-кейсы в соответствии с майнд-картой.
Тест-кейсы можно посмотреть тут

## Баг-репорты

## Коллекции POSTMAN

## Автотесты

