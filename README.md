# Тестовое задание

Давайте реализуем упрошенную версию 2Гис справочника. Предполагаемая аудитория 1 000 000 пользователей в месяц. Размер базы фирм составляет порядка 100 000 записей.
Наш справочник будет имеет 3 вида объектов:
* Фирма
* Здание
* Рубрика

### Функции каталога
Взаимодействие с пользователем происходит посредством HTTP запросов к API серверу. Все ответы представляют собой JSON объекты.
Сервер реализует следующие методы:
* выдача всех организаций находящихся в конкретном здании
* список всех организаций, которые относятся к указанной рубрике
* список организаций, которые находятся в заданном радиусе/прямоугольной области относительно указанной точки на карте.
* список зданий
* выдача информации об организациях по их идентификаторам
* дерево рубрик каталога со всеми предками, с возможностью фильтрации по потомкам конкретного узла
* поиск организации по названию
* рубрикатор каталога сделать с произвольным уровнем вложенности рубрик друг в друга

## Документация

[Ссылка на документацию](http://85.143.210.108/doc)

# Зависимости

    Docker Engine 1.10.0+
    Compose 1.6.0+

# Установка

    git clone https://github.com/NikitaObukhov/2gis-docker
    cd 2gis-docker
    docker-compose up -d
    docker exec 2gis_web composer install
    docker exec 2gis_web bin/console doctrine:database:create
    docker exec 2gis_web bin/console doctrine:schema:create
    docker exec 2gis_web bin/console doctrine:fixtures:load
    docker exec 2gis_web chmod -R 777 var/cache var/logs var/sessions

Приложение будет доступно по адресу http://localhost/doc а также по адресу http://localhost:668/doc (минуя кэширующий прокси). Если 80-й порт занят другим процессом, вы можете изменить его в docker-compose.yml
# Установка вручную

[Для установки вручную](https://github.com/NikitaObukhov/2gis)
