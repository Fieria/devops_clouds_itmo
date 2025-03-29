# Лабораторная работа 2. Сравнение сервисов Amazon Web Services и Microsoft Azure. Создание единой кросс-провайдерной сервисной модели.

Вариант 7

## Значение полей в Azure Billing

Поле в биллинге       | Описание                                                                 | Пример значения                         |
|---------------------------|--------------------------------------------------------------------------|--------------------------------------------------|
| **IT Tower**             | Высокоуровневая классификация ИТ-услуг                                  | `Compute`, `Storage`, `Networking`, `Databases`  |
| **Service Family**       | Группа связанных сервисов Azure                                         | `Virtual Machines`, `Storage`, `SQL Database`    |
| **Service Type**         | Конкретный вид сервиса в рамках Service Family                         | `Virtual Machines`, `Blob Storage`, `Cosmos DB`  |
| **Service Sub Type**     | Подтип услуги — дополнительная детализация                             | `D4s v3`, `Standard LRS`, `Provisioned Throughput` |
| **Service Usage Type**   | Модель использования (Pay-as-you-go, Reserved, Spot)                   | `Pay-As-You-Go`, `Reserved`, `Spot`              |
## Сервисы, которые представлены в биллинге

* `SQL Database` - Fully managed relational database service (PaaS) with auto-scaling
* `SQL Data Warehouse` - Cloud analytics warehouse (now part of Azure Synapse Analytics)  
* `Storage` - Core Azure storage services (Blob, File, Queue, Table)
* `Virtual Machines Licenses` - Software licenses for Azure VMs (Windows, SQL Server etc)
* `Virtual Machines` - Cloud virtual servers (IaaS solution

## Результат работы

