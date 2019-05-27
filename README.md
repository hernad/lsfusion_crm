Построена на базе платформы [lsFusion](https://github.com/lsfusion/platform).

# Возможности

* Ведение клиентов, организаций, а также контактных лиц по ним.
* Поддержка нескольких собственных компаний.
* Работа с договорами, соглашениями и актами.
* Возможность генерации документов на основе шаблонов (Word) и заготовок.
* Ввод/импорт оплат клиентов и собственных платежей из бухгалтерского контура.
* Контроль рабочего времени сотрудников. Поддержка отпусков, больничных, отгулов. Импорт из Redmine.
* Поддержка разных валют.
* Поддержка расходов по сотрудникам. Расчет прибыли по клиентам.
* Регистрация событий по клиентам.

# Демо

Демо-версия с наполненной тестовой базой данных находится по адресу https://demo.lsfusion.org/crm.

В примере введены пользователи с разными ролями и доступными формами.

Доступные логины :
* admin - Администратор (полный доступ ко всем функциям)
* owner - Учредитель
* manager - Менеджер
* accountant - Бухгалтер
* employee - Сотрудник

Пароли совпадают с логинами.

Изменять роли и их права можно под администратором на форме Администрирование / Политика безопасности.

Данные введены в основном за 2018 год. Во всех формах лучше всего выбирать соответствующий период.

# Инсталляция

* Устанавливаем lsFusion на сервер, как описано в следующей инструкции : https://documentation.lsfusion.org/pages/viewpage.action?pageId=57738078.
* В папке /var/lib/lsfusion запускаем git pull.
* В файле /etc/lsfusion2-server/lsfusion.conf добавляем в значение параметра CLASSPATH следующий путь - /var/lib/lsfusion/crm/src/main/resources (перед ним двоеточие).
* Перезапускаем сервер lsFusion (как в первой инструкции).

# Краткое описание

Основные рабочие формы расположены на вкладке Рабочий стол. Каждая из них предназначена для выполнения определенного процесса(ов).

## Работа с клиентами

Форма предназначена для удобного отображения и редактирования всей информации по одному клиенту. 

## Работа с договорами

Показывает список всех активных договоров с возможностью их редактирования и просмотром всей детальной информации, привязанной к договорам.

## Работа с задолженностями

### Контроль задолженности

Отображает список задолженностей по всем договорам клиентов. Идет автоматический расчет суммы оплаты по каждой задолженности с учетом привязки к договорам/соглашения/актам по принципу FIFO. На форме можно выставить акт по одной или нескольким задолженностям в рамках одного договора.

### План платежей

Показывает помесячно задолженности (будущие и текущие) в разрезе типов договоров, а также произведенные оплаты.

## Итоги работы

### Прибыль по клиентам

Рассчитывает за выбранный интервал доходы, расходы и прибыль в валюте. Доходы рассчитываются как все платежи по курсу на дату оплаты. Расходы рассчитываются исходя из отмеченного времени сотрудников по клиентам исходя из сумм, заданных в форме Расходы по сотрудникам. Также отмеченное время по проектам без клиента (внутренним проектам) может "расписываться" на всех клиентов пропорционально доходам относительно групп договоров.

### Прибыль по месяцам

Сводит в одну форму доход и расходы по месяцам в валюте. Подбиение итогов в разрезе типов и групп договоров.

### Отчет менеджера

Выводит в Excel файл список всех платежей по клиентам, привязанных к определенному сотруднику с заданной ролью (например, к роли Менеджер).

## Работа с документами

### Обработка платежей

Используется для импорта из бухгалтерской системы платежей клиентов и исходящих платежей с последующей обработкой. Как правило, в процессе обработки идет привязка платежей к договорам, соглашениям и актам.

### Обработка документов

Показывает список всех рабочих документов (договора, соглашения, акты) в системе в единой таблице. Предназначена для работы со входящей и исходящей корреспонденцией. В этой форме можно отмечать даты и способы отправки документов, закрывать обработанные.

### Итоги по актам

Отображает суммы выставленных актов по месяцам в разрезе организаций. Используется бухгалтерами для проверки корректности выставленных актов.

## Рабочее время

### Табель рабочего времени

Предназначена для отметки сотрудниками времени, затраченного по конкретным клиентам, а также регистрации отпусков, больничных и прочих причин остуствия на рабочем месте. Если осуществляется автоматический импорт из внешней системы отметки времени (например, Redmine), то в форме отображаются также и импортированные отметки времени.

### Контроль отмеченного времени

Показывает в виде таблицы отмеченное время и отсутствие каждого сотрудника за определенный месяц. Необходима для контроля менеджером правильности заполнения табеля рабочего времени сотрудниками.

### Выставление счетов

В этой форме можно формировать по каждому клиенту Excel файл за заданный интервал со списком всех трудозатрат. Также присутствует возможность привязывать задачи к конкретным договорам и соглашениям.

## Прочее

### Обработка событий

На этой форме пользователи могут регистрировать события (звонки, переговоры, презентации и т.д.) связанные с определенными клиентами. Также в ней можно отслеживать время необходимости следующего контакта с клиентом, если это было помечено ранее, через отбор Последние по клиенту.

### Мои задачи

Предназначена для создания задач другим сотрудниками и изменению назначенных текущему пользователю задач. Показываются только задачи не импортированные из внешних систем (например, Redmine)

