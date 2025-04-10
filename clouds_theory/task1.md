# Рубежная работа 1. Вариант 7.
Опишите бессерверные вычисления. Как это так, вычисления без сервера?
##

`Вычисления (Compute)` - это базовый сервис, который представлен в облаке.

Существует три модели предоставления облачных сервисов пользователю - 
* IaaS (Infrastructure as a Service)
* PaaS (Platform as a Service)
* SaaS (Software as a Service)

В контексте Compute эти модели реализуются как предоставление пользователю-
* IaaS -> виртуальных машин
* PaaS -> CaaS (Containers as a Service, т.е. готовых контейнерных сред)
* SaaS -> FaaS (Function as a Service, т.е. сред для выполнения функций/лямбд)

`Бессерверные вычисления (Severless)` - это как раз и есть модель FaaS. В такой модели сервис предоставляет пользователю готовую среду, где можно выполнить свои функции (вычисления), а управление всей инфраструктурой 'под капотом' осуществляет провайдер. Причем, сервис не предоставляет полноценную IDE, а только платформу для `выполнения` кода + ограниченный редактор для мелких правок.

Другими словами, пользователь не видит и не управляет физическими серверами, виртуальными машинами, контейнерами или ОС. Пользователь просто загружает свой код в облачный FaaS сервис, а сервис самостоятельно выделяет ресурсы для выполнения кода.

Почему же вычисления называют бессерверными? Потому что сервис выделяет ресурсы (СPU, RAM) `только на время выполнения лямбды`, а после ресурсы `освобождаются`. У пользователя нет «постоянно выделенных» серверов (инфраструктуры) под его функции.

## Важные моменты, которые следует уточнить:
- при Stateless-модели каждый вызов функции выполняется изолированно, т.е. данные не сохраняются и не передаются между вызовами
- однако бессерверные функции могут читать/писать данные во внешние хранилища
- но на время выполнения вычислений данные, конечно же, сохраняются в облачных хранилищах провайдера
- при Stateless-модели ресурсы "не простаивают", пользователь платит только за время выполнения функций

## Вывод
Вычисления называются бессерверными, потому что пользователь получает ресурсы сервера `только на время выполнения своей функции`, а потом ресурсы сразу освобождаются. При этом сервер физически существует, но пользователь от него абстрагирован.
