### Тестовое задание на позицию JS / TS Fullstack Developer

#### Закончив реализацию, открывайте Pull Request в этот репозиторий

Этот репозиторий содержит рабочее базовое приложение, в которое предлагается нарастить функциональность.
Приложение во многом похоже на то, с чем вам предстоит работать в QIWI.

Для затравочки: в базе данных лежат платёжные данные о пополнениях счетов мобильных операторов по одному из интерфейсов QIWI.
Эти данные нужно будет отдать по API. Для внимательных есть пасхалка: среди транзакционных данных закралась реальная аномалия. Нашедшему жирный плюс =)

#### Для выполнения задания нужно добавить метод контроллера в авторизованной зоне, выдающий содержимое таблицы aggr_bills.
Большим плюсом будет реализация фильтров по дате в качестве параметров запроса.

Схема БД содержит две таблицы: obj_user и aggr_bills. Таблицы никак не связаны.

В таблице obj_user лежит список пользователей. Запросы на выборку из неё реализованы в приложении. Этой функциональностью следует пользоваться как примером.
 
Во таблице aggr_bills лежат платёжные данные в виде транзакционных агрегатов по пятиминутным интервалам. Доступ к данным в этой таблице необходимо реализовать. 

В текущей реализации приложение может авторизовать пользователя, 
а также в авторизованной зоне выдать список пользователей и информацию о конкретном пользователе по его id.

Рекомендуется пользоваться [API-документацей](https://qiwi.github.io/test_task_node_server/)

Для авторизации служит [POST метод Auth](https://qiwi.github.io/test_task_node_server/#api-Auth) с параметрами:
```
email: candidate@e.ru
password: candidate
```

Полученный при авторизации JWT-токен потребуется для доступа к [запросам авторизованной зоны](https://qiwi.github.io/test_task_node_server/#api-User)

JWT-токен необходимо указать в заголовке Authorization после ключевого слова Bearer.

Все креды для подключения к БД есть в [config/default.json](https://github.com/qiwi/test_task_node_server/blob/master/config/default.json)

#### Для первого запуска приложения достаточно трёх шагов:
*при условии установленной среды Node.js >= 8.11

установить зависимости

```
npm install
```
собрать приложение
```
npm run build
``` 
и запустить
```
npm start
```

#### Линтер
Линтёр - это хорошо. 

Пользуемся им так:
```
npm run lint
```
Перед коммитами стараемся не забывать его прогонять.