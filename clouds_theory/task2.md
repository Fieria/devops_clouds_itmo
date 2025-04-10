# Рубежная работа 1. Вариант 4.

Какие есть способы экономить в облаке? Объясните подробно разницу между моделью
использования по требованию (on demand) и резервацией мощностей (reserved). Есть ли другие
модели использования облака
##


## Услуги облачных провайдеров можно приобрести в соответствие со следующими моделями:
`1. Модель использования по требованию (On-Demand)`

Усулга предоставляется немедленно по запросу клиента. Причем пользователь в режиме реального времени может отменить ресурсы (отказаться от услуг) или изменить объем ресурсов (конфигурацию). Т.е пользователь не обязан придерживаться како-то определенного графика по ипсользованию ресурсов. 

Такая модель может быть и внеоблачных сервисах. Например, каршеринг.

Преимущества:
-  Нет обязательств (подходит для нестабильных нагрузок)
-  Гибкость (в любой момент можем уменьшить/увеличить ресурсы)
-  Быстрый страт (не нужно планировать заранее)

Минусы:
- Самая высокая стоимость

Для чего подходит:
- Краткосрочные проекты
- Непредсказуемые нагрузки (пиковые периоды)
- Тестирование новых сервисов

##
`2. Резервирование мощностей (Reserved Instances)`

Пользователь резервирует ресурсы на определённый срок (обычно 1-3 года) по сниженной цене по сравнению с оплатой on-demand. Иногда скидка на резервирование может достигать до 90%. Существенная экономия!

Преимущества:
- Существенная экономия
- Гарантированная доступность

Минусы:
- Обязательства (нельзя отменить или нужно платить штраф за досрочное прекращение)
- Планирование (нужно зарание расчитать, сколько ресурсов понадобиться проекту)

Для чего подходит:
- Для долгосрочных проектов
- Для стабильные нагрузок (особенно если они 24/7)

##
`3. Бессерверные вычисления (Serverless)`

Пользователю предоставляется уже готовая среда среда для выполнения его функций. Пользователь патит только за время выполнения его кода.

Преимущества:
- Экономия за счет времени использования
- Не нужно управлять инфраструктурой
- Гибкость

Минусы:
- Не подходит для полноценных проектов
- Возможны ограничения по времени испольнения кода
- Данные хранятся в облаке только на время выполнения функции (а потом ресурся провайдера очищаются)

Для чего подходит:
- Обработка событий (Lambda функции)
- Микросервисы

##
`4. Dedicated Hosts (Выделенные серверы)`

Физические серверы арендуются исключительно одним клиентом (без соседства с другими).

Преимущества:
- Полная изоляция = безопасность (например, для банков)
- Контроль над размещением VM
- Стабильность/предсказуемая производительность без "соседей"

Минусы:
- Высокая стоимость
- Необходимость в высококвалифицированных сотрудников (т.к. часть функций провайдера клиент теперь выполняет сам)

Для чего подходит:
- Масштабные и сложные проекты, требующие повышенной безопасности
- Highload-системы
- Если мы хотим создать гибридное облако (можно, конечно, выспользоваться и предыдущими моделями, но Dedicated Hosts самый распространенный)
- Лицензионно-зависимые системы (это когда наш продукт юридически привязан к конкретным физическим ресурсам согласно условиям лицензионного соглашения)

Например, такую модель могут использовать госструктуры, банки, медицинские учреждения

##
`Spot Instances (Прерываемые инстансы)`

Пользователь арендует облачные серверы с огромной скидкой (например, 90% по сравнению с On-Demand), НО эти серверы могут в любой момент исезнуть. Т.е. если провайдеру понадобятся ресурсы, то он может в любой момент прервать услугу насовсем (удалить инстанс) или преостановить на время (обычно провайдер дает пользователю 2 минуты на  завершение своих задач).

Преимущетсва:
- Огромная экономия

Недостатки:
- Потеря данных при прерывании инстанса (нужно сохранять данные во внешнее хранилище)
- Непредсказуемая доступность сервиса

Для чего подходит:
- Задачи, которые можно перезапустить (тестирование кода, сборка программ)

`Как примерно работает ценообразование Spot Instances:`

Если спрос на On-Demand небольшой, то у провайдера появляются свободные мощности. Как же тогда на них заработать? Использовать Spot Instances! А дальше начинается нечто, похожее на аукцион:

Провайдер устанавливает цену на спотовые инстансы. Вы и другие пользователи предлагают максимальную цену, которую готовы заплатить за спотовый инстанс. Если вы указали цену больше или равную провайдерской, то ваш инстанс запускается. Причем вы платите не ту цену, которую предложили, а ту, которую предложил провайдер.

Но вдруг у провайдера увеличился спрос на On-Demand и теперь ему нужно забрать часть спотовых инстансов. У кого же заберут ресурсы - у вас или у другого пользователя спотов? Если другой пользователь был готов заплатить цену больше, чем вы, то ресурсы отключат у вас и передадут для On-Demand. И еще провайдер обновит цены на спотовые инстансы (увеличит), например, до стоимости, которую платит тот самый пользователь, которому вы 'проиграли'. Вот такие пироги)

## Вывод по сравнению моделей On-Demand и Reserved Instances

- Модель On-Demand предлагает гибкость (быстрая адаптация при изменении задач и требований к инфраструктуре) и эластичность (автоматическое масштабирование), но более высокую цену.
- Модель Reserved Instances предлагает низкую цену, но отсутствие гибкости и эластичности (т.е. мы зарание выбрали и зафиксиривали инфраструктуру и не можем отказаться от ее использования)

## Как экономить в облаке

- `Удалять ненужные данные, оптимизировать использование облачного хранилища`

Например, если мы пользуемся хранилищем S3, то логи стоит хранить в дата-центрах стандарта S3 Glaizer или S3 Glaizer Deep Archive. Да, если нам понадобиться вытащить данные оттуда, то это может занять аж несколько часов, зато мы СУЩЕСТВЕННО выиграем в стоимости (ну вообщем останемся в плюсе, если данные нам надо вытаскивать очень редко или почти никогда).

- `Использовать CDN (Content Delivery Network)`

Благодаря CDN мы меньше платим за работу полос пропускания сети (передачу данных по сети). Грубо говоря, данные 'проходят меньшее расстояние' по сети + исходный сервер разгружается. Но конечно наша выгода/невыгода зависит от настройки CDN

- `Использовать Serverless Compute/Бессерверные вычисления/FaaS`

Платим только за время выполнения функций и инфраструктура "не простаивает"

- `Выбирать правильную модель оплаты` для каждого сервиса по отдельности (Compute, Storage, Networking, AI/ML)

Предыдущий пункт можно назвать подпунктом этого*

- `Использовать автоматизацию`

Например, Terraform, Kubernetes снижают расходы на администрирование

- `Использовать гибридное облако`

При правильно выстроенной инфраструктуре и мониторинге затрат, разумеется

- `Мониторить затраты`

Тут без комментариев
