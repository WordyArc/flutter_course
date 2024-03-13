# Лабораторная работа на семестр

В рамках курса необходимо разработать одно приложение со списком задач. Разработка осуществляется с помощью 
системы контроля версий git. Задания выполняются последовательно в отдельных ветках, при сдаче осуществляется 
pull request в основную ветку проекта. Каждое задание представляет собой некоторую часть проекта.

_**Примечание: сторонние библиотеки, кроме тех, что указаны в задании запрещены.**_

## Задание 1. Верстка экрана категории задач

В рамках первого задания необходимо: 

### Категории
* сверстать экран категорий задач (например дом, работа, учеба и пр.)  
* реализовать функционал добавления, удаления, изменения категорий.

### Задачи
* сверстать экран списка задач выбранной категории.
* реализовать функционал добавления, удаления.
* реализовать фильтрацию. Варианты для фильтров: 
  * Все
  * Завершенные
  * Незавершенные
  * Избранные

Приблизительное описание объектов для работы:

    Категория
    id: string - Генерировать при помощи пакета uuid, использовать uuid.v4;
    name: string;
    createdAt: DateTime - брать текущую дату и время. DateTime.now();
___
    Задача
    id: string - Генерировать при помощи пакета uuid, использовать uuid.v4;
    title: string;
    description: string;
    isCompleted: bool;
    isFavourite: bool;
    createdAt: DateTime - брать текущую дату и время. DateTime.now();
    categoryId: string - ссылка на категорию, к которой принадлежит задача;

#### Список категорий задач
![simulator_screenshot_8CA21849-E3DB-4569-B199-04465B77FC19.png](assets%2Fcategories%2Fsimulator_screenshot_8CA21849-E3DB-4569-B199-04465B77FC19.png)
![simulator_screenshot_955F5A6A-7DE1-4039-A825-A80983BA6F42.png](assets%2Fcategories%2Fsimulator_screenshot_955F5A6A-7DE1-4039-A825-A80983BA6F42.png)
![simulator_screenshot_D18A7D69-83D7-4ED6-A3A4-4EA31B5D93E9.png](assets%2Fcategories%2Fsimulator_screenshot_D18A7D69-83D7-4ED6-A3A4-4EA31B5D93E9.png)
![simulator_screenshot_1343577B-4F35-45E0-9747-77A8C987C118.png](assets%2Fcategories%2Fsimulator_screenshot_1343577B-4F35-45E0-9747-77A8C987C118.png)
![simulator_screenshot_C5F39C72-7A3C-41CB-B5E0-1EE9CB69444A.png](assets%2Fcategories%2Fsimulator_screenshot_C5F39C72-7A3C-41CB-B5E0-1EE9CB69444A.png)

#### Список задач
![simulator_screenshot_1AA41746-55E6-4D40-8897-9B971A1291E6.png](assets%2Ftasks%2Fsimulator_screenshot_1AA41746-55E6-4D40-8897-9B971A1291E6.png)
![simulator_screenshot_955E006B-2183-4FC3-A119-464BDC181F3C.png](assets%2Ftasks%2Fsimulator_screenshot_955E006B-2183-4FC3-A119-464BDC181F3C.png)
![simulator_screenshot_9D40DC2C-9B92-4FC8-8AE9-10B27E1CB9E5.png](assets%2Ftasks%2Fsimulator_screenshot_9D40DC2C-9B92-4FC8-8AE9-10B27E1CB9E5.png)
![simulator_screenshot_CC7562EE-DA79-404D-B186-C1959BDCC8E9.png](assets%2Ftasks%2Fsimulator_screenshot_CC7562EE-DA79-404D-B186-C1959BDCC8E9.png)

## Задание 2. Верстка экрана задачи

В рамках второго задания необходимо:

* сверстать экран задачи, реализовать функционал удаления, редактирования заголовка и описания задачи.

#### Экран задачи
![simulator_screenshot_50D595A4-20C7-461A-83FB-CB4D5469EA14.png](assets%2Ftask%2Fsimulator_screenshot_50D595A4-20C7-461A-83FB-CB4D5469EA14.png)
![simulator_screenshot_B3615767-9923-4B74-9A55-ECFE25913AC3.png](assets%2Ftask%2Fsimulator_screenshot_B3615767-9923-4B74-9A55-ECFE25913AC3.png)

## Задание 3. Архитектура

В рамках третьего задания необходимо:
* разбить код на три слоя в соответствии с Clean Architecture;
* использовать для обращения к данных паттерн «репозиторий»;
* использовать паттерн «сервис локатор» для регистрации и получения зависимостей;
* вынести логику из виджетов в BLoC.


Структура получившегося проекта должна быть примерно следующей:
```Bash
lib
├── core
├── data
│   ├── datasources
│   ├── mappers
│   ├── models
│   └── repositories
├── domain
│   ├── entities
│   ├── repositories
│   └── usecases
└── presentation
    ├── cubits
    ├── blocs 
    ├── screens
    └── widgets
```

Для внедрения зависимостей использовать одну из следующих библиотек на выбор:
**get_it**, **provider**, **injectable**, **riverpod**.

Для управления состоянием использовать пакет **flutter_bloc**.

## Задание 4. База данных

В рамках четвертого задания необходимо:
* перевести хранение данных из оперативной памяти в SQL базу данных;
* для работы с базой данных использовать одну из ORM библиотек на выбор: **drift**, **floor**.

## Задание 5. Добавление фотографий

В рамках пятого задания необходимо добавить функционал прикрепления фотографий к задаче. 
Фотографию можно получить добавив из Flickr, или любого другого ресурса картинок.
Для работы с Flickr необходимо отправлять запросы и реализовать пагинацию.

Ресурсы, которые могут помочь:
- https://www.flickr.com/services/api/request.rest.html - REST формат flickr
- https://www.flickr.com/services/api/misc.api_keys.html - получение api key для flickr
- https://www.flickr.com/services/api/ - flickr api (нам нужен метод photos.search)
- https://www.flickr.com/services/api/explore/flickr.photos.search - explorer с помощью которого можно повызывать методы api


Для работы с сетью использовать один из пакетов на выбор: http, dio.
