# Аттестационное задание. "Классика". 27.10.2020

- [Репозиторий](#репозиторий)
- [Запуск и работа с проектом](#запуск-и-работа-с-проектом)
- [Задание](#задание)
- [Завершение работы](#завершение-работы)

## Репозиторий

Текущий репозиторий будет доступен до завершения срока задания.

Сделайте форк текущего репозитория в свой GitHub аккаунт.  
_Если у вас нет аккаунта - настало время его создать))_ 

---

## Запуск и работа с проектом

**Устанавливаем зависимости**

```bash
npm i --save-exact
```

**Запускаем сборку**

```bash
npm run dev
```

**Рабочая директория**

Все исходные ресурсы, включая разметку, находяться в директории `src/`.  
Работаем только в этой директории.

Финальной сборки по заданию выполнять не нужно.  
Физических файлов сборки также не будет, вся сборка в памяти на основе `webpack-dev-server`

**Стили**

В проекте используется пакет `microbe-ui`.  
Здесь вы можете вытащить привычные миксины и функции для Sass.  
Все они начинаются с `microbe-*`.  
Нужно больше - пишем сами, копируем с других проектов и тд.

**Скрипты**

В проекте подключена библиотека jQuery.  
Рекомендуем всю реализацию писать с ее использованием.
Также есть пример рекомендуемой организации кода.

**Разметка**

Работаем с чистым HTML.  
Без шаблонизаторов!  
Да, хардкор)  
Но для объема текущего задания вполне подходящий

---

## Задание


> Необходимо закончить работы по верстке условной страницы "списка товаров".

**1. Написать обработчик фильтра.**

При каждой смене контрола необходимо собрать данные формы и подготовить для отправки.  
Структура данных должна быть следующей

```
{
  params: {
    brand: [string, string, ...],
    manufacturer: string,
    model: string,
    year: number,
    price: [number, number]
  },
  pagination: {
    sort: string
    perPage: number
    page: number
  }
}
```

Сама "отправка данных" выполняться не будет.
Полученную структуру вам нужно просто вывести через `console.log(data)`

**2. Добавить недостающие элементы разметки**

1. В фильтре добавить выбор года.
    - значения от 1976 по 2021 год
    - каждую декаду сгруппировать, по примеру 70-ые, 80-ые, 90-ые, 2k, 2k10 и 2k20
2. После списка товаров добавить разметку пагинации под программирование
    - схема разметки << | < | 1 | 2 | 3 | 4 | 5 | > | >>
    - адреса в ссылках просто `#`
    - в разметке нужно продемонстрировать активную страницу: стилизация и отсутствие атрибута `href`

**3. Составить GET-параметры для адресной строки**

1. Данные с формы нужно перевести в форматированную строку.
    - если параметр имеет несколько значений он должен дублироваться в строке
    - пустые параметры не используются в строке
2. Параметры должны быть в отсортированном порядке
    1. `page`
    1. `year`
    1. `price`
    1. `model`
    1. `manufacturer`
    1. `brand`
    1. `sort`
    1. `per-page`
3. После получения строки - необходимо вставить GET-параметры в адресную строку
    - без перезагрузки страницы
    - с сохранением браузерной истории, должна быть возможность вернуться назад

---

## Завершение работы

1. Выполните финальную сборку
    - `npm run test`
    - `npm run build`
1. Должны получить файлы сборки внутри новой директории `docs/`
    - да, `docs`, все норм))
    - коммитим файлы сборки и отправляем на мастер
1. В настройках своего репозитория включаем публикацию GitHub pages
    - Ветка `master`
    - Директория `docs`, _вот оно зачем))_
    - Тема - не выбираем
1. Через пару минут, ваша ссылка будет доступна, например `https://user-name.github.com
/repo-name/`
1. Проверить в настройках проекта чтобы был включен баг-трекер
    - `Settings/Features/Issues`
1. Отправляем ссылки в соответствующую задачу Worksection
    - ссылка на репозиторий
    - ссылка на GitHub pages

