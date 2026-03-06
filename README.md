# Домашнее задание к занятию 15 «Система сбора логов Elastic Stack» - `Иншаков Владимир`

## Задание 1

Вам необходимо поднять в докере и связать между собой:

- elasticsearch (hot и warm ноды);
- logstash;
- kibana;
- filebeat.

Logstash следует сконфигурировать для приёма по tcp json-сообщений.

Filebeat следует сконфигурировать для отправки логов docker вашей системы в logstash.

В директории [help](./help) находится манифест docker-compose и конфигурации filebeat/logstash для быстрого 
выполнения этого задания.

Результатом выполнения задания должны быть:

- скриншот `docker ps` через 5 минут после старта всех контейнеров (их должно быть 5);
- скриншот интерфейса kibana;
- docker-compose манифест (если вы не использовали директорию help);
- ваши yml-конфигурации для стека (если вы не использовали директорию help).

## Решение задания 1

Результат команды `docker ps` для контроля запущенных контейнеров:
![Screen01](https://github.com/MrVanG0gh/Netology_monitoring_03/blob/main/Screens/Screen01.png)
Здесь мы видим пять котейнеров для ELK-стека и 1 контейнер с dummy-приложением.

Скриншот домашней страницы kibana:
![Screen02](https://github.com/MrVanG0gh/Netology_monitoring_03/blob/main/Screens/Screen02.png)

---

## Задание 2

Перейдите в меню [создания index-patterns  в kibana](http://localhost:5601/app/management/kibana/indexPatterns/create) и создайте несколько index-patterns из имеющихся.

Перейдите в меню просмотра логов в kibana (Discover) и самостоятельно изучите, как отображаются логи и как производить поиск по логам.

В манифесте директории help также приведенно dummy-приложение, которое генерирует рандомные события в stdout-контейнера.
Эти логи должны порождать индекс logstash-* в elasticsearch. Если этого индекса нет — воспользуйтесь советами и источниками из раздела «Дополнительные ссылки» этого задания.
 
## Решение задания 2

![Screen03](https://github.com/MrVanG0gh/Netology_monitoring_03/blob/main/Screens/Screen03.png)
![Screen06](https://github.com/MrVanG0gh/Netology_monitoring_03/blob/main/Screens/Screen06.png)
Согласно заданию были добавлены два индекс-паттерна "index1" и "index2"

![Screen04](https://github.com/MrVanG0gh/Netology_monitoring_03/blob/main/Screens/Screen04.png)
Здесь можно видеть как идет накопление логов с течением времени

![Screen05](https://github.com/MrVanG0gh/Netology_monitoring_03/blob/main/Screens/Screen05.png)
Здесь используется фильтр `container.image.name.keyword : *alpine` для ограничения выборки

---

### Как оформить решение задания

Выполненное домашнее задание пришлите в виде ссылки на .md-файл в вашем репозитории.

---

 