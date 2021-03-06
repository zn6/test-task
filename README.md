# Тестовое задание компании ООО «Резольвента» 

Требуется разработать небольшой веб сервис, который будет отвечать за расчет рабочего расписания сотрудников.

## Расписание сотрудника компании

Сервис на вход получает период дат и id работника в качестве get параметров: `employeeId`, `startDate`, `endDate`.

В ответ сервис должен отправить рабочее расписание сотрудника в формате JSON. В расписание не должны попасть: 

- праздничные и выходные дни

- обеденный перерыв

- время до начала рабочего дня и после рабочего дня

Пример ответа: 

```
GET http://localhost/employee-schedule?startDate=2021-01-01&endDate=2021-01-12&employeeId=1
{
   "schedule": [
      {
         "day":"2021-01-11",
         "timeRanges": [
            {
               "start":"10:00",
               "end":"13:00"
            },
            {
               "start":"14:00",
               "end":"19:00"
            }
         ]
      },
      {
         "day":"2021-01-12",
         "timeRanges": [
            {
               "start":"10:00",
               "end":"13:00"
            },
            {
               "start":"14:00",
               "end":"19:00"
            }
         ]
      }
   ]
}
```

Для исключения из рабочего расписания праздничных дней используйте любой открытый API источник (например, Google calendar API, xmlcalendar.ru, isdayoff.ru...).

Работу с базой данных реализовывать не обязательно, однако, подумайте, как вы будете хранить информацию о графике работы сотрудника.

В качестве индивидуальных данных работника используйте следующие параметры (или любые подобные):

Работник №1

- График (10:00 - 13:00 [обед] 14:00 - 19:00).

- Рабочие дни с понедельника по пятницу.

Работник №2

- График (09:00 - 12:00 [обед] 13:00 - 18:00).

- Рабочие дни с понедельника по пятницу.


## Требования и пояснения к задаче

- Код должен быть написан в ОО стиле, быть чистым и хорошо читаться.

- При выполнении задания можно использовать любое открытое ПО (фреймворки, компоненты).

- Плюсом будет покрытие кода автоматическими тестами и выполнение дополнительного задания.

## Дополнительное задание

Добавить endpoint, который по тем же входным параметрам вернет нерабочее расписание работника (в том же формате, что и рабочее расписание)

## Каркас приложения

Что бы не тратить время на инфраструктуру, Вы можете воспользоваться одной из подготовленных заготовок:

- [Symfony](https://github.com/ResolventaGroup/symfony-test-task-skeleton)

- [Laravel](https://github.com/ResolventaGroup/laravel-test-task-skeleton)
