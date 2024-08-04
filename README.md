# Скрипт по сбору кластеров запросов на основе данных Яндекс.Вебмастера.

## Описание и задачи скрипта
Мониторинг запросов из Я.ВМ предоставляет интересную информацию по запросам и страницам, но связывает их у себя только под капотом. Из интерфейса выкачать связку URL - Список запросов не получится, а хотелось бы. 
Этот скрипт позволяет взаимодействовать с API Яндекс и обрабатывать данные.

## Шаг 1: Создание приложения в Яндекс ID

1. Перейдите по ссылке для создания нового приложения в Яндекс ID: [Создать приложение](https://oauth.yandex.ru/client/new).
2. Введите произвольное название для приложения, например, `YaWM-Clusterer`.
3. В разделе "Платформы приложения" выберите "Веб-сервисы".
4. В разделе "Доступ к данным" выберите "Добавление сайтов в Яндекс.Вебмастер ...".
5. Нажмите кнопку "Создать приложение".

## Шаг 2: Получение токена

1. На следующей странице после создания приложения скопируйте `Client_ID`.
2. Подставьте свой `Client_ID` в следующий URL: https://oauth.yandex.ru/authorize?response_type=token&client_id={CLIENT_ID}
3. Замените `{CLIENT_ID}` на скопированный идентификатор.
3. Перейдите по этому URL в вашем браузере, авторизуйтесь и получите уникальный токен.
4. Скопируйте полученный токен. Он потребуется для настройки скрипта.

## Шаг 3: Настройка скрипта

1. Вставьте ваш токен в скрипт. Найдите строку, где требуется указать токен, и замените её на ваш уникальный токен.
2. Установите необходимые библиотеки, выполнив следующую команду:
```bash
pip install requests pandas openpyxl pyfiglet
```

## Шаг 4: Подготовка файла stoplist.txt
1. Рядом со скриптом должен находиться файл stoplist.txt.
2. В этом файле на каждой строке указывайте стоп-слова. Это поможет фильтровать ненужные поисковые запросы.
