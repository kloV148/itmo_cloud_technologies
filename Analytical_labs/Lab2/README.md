## Аналитическая работа 2

### Цель работы

Знакомство с облачными сервисами.
Понимание уровней абстракции над инфраструктурой в облаке.
Формирование понимания типов потребления сервисов в сервисной-модели.
Сопоставление сервисов между разными провайдерами.
Оценка возможностей миграции на отечественные сервисы.

### Ход работы

Мы выделили сервисы, которые нам встретились.
Ниже будет представлено их описание.

### Список сервисов и их описание

**Microsoft Analysis Services** - подсистема управления данными,
которая позволяет проводить анализ, создавать модели и разрабатывать отчеты.
Её службы доступны в следующих сервисах:

- Azure Analysis Services
- Power BI Premium
- SQL Server Analysis Services

**Azure Data Factory** - облачный сервис, который позволяет интегрировать
и трансформировать данные из различных источников. Он предоставляет средства для создания,
планирования и управления потоками данных в облаке и между облаками. Для получения
бизнес аналитики эти данные можно передавать в Azure Synapse Analytics.

**Azure SQL Database** - управляемая облачная база данных.
Она представляет собой полностью управляемую службу баз данных, которая обеспечивает высокую производительность,
безопасность и масштабируемость. В зависимости от потребностей разделяется на
следующие tiers:

- general purpose
- business critical
- hyperscale

**Azure Cache for Redis** - хранилище данных в памяти на основе Redis.
Способно значительно увеличит производительность приложений и его масштабируемость.
Среди основных сценариев использования предполагается:

- кэширование данных
- кэш содержимого
- сессионное хранилище
- очередь сообщений и задач
- распределение транзакций

Доступен в следующих tiers:

- Basic
- Standard
- Premium
- Enterprise
- Enterprise Flash

**Azure CDN** - сеть доставки содержимого. Представляет собой
распределенную сеть серверов, которая позволяет быстро доставлять
статические содержимое пользователям по всему миру. Сеть CDN хранит кэшированное содержимое на пограничных серверах в
расположениях
точки присутствия (POP),
расположенных близко к конечным пользователям, чтобы свести к минимуму задержку.

**Azure Batch** - платформа для выполнения параллельных и высоконагруженных вычислений в облаке.
Она предоставляет API для создания и выполнения заданий, которые могут выполняться на любом количестве
виртуальных машин в облаке.

**Compute instances** - виртуальные машины, которые предоставляются в облаке.
Могут быть на базе Linux или Windows. Доступны в разных конфигурациях в зависимости от
выполняемых задач.

**Azure Data Box** - физическое устройство, которое позволяет быстро и безопасно
перенести большие объемы данных в облако Azure или из облака Azure.

**Azure Key Vault** - решение созданное для решения следующих задач:

- управлениями ключами
- управлениями секретами
- управлениями сертификатами

Предлагает стандартный уровень (шифруется с использованием программного ключа)
и премиум уровень (включает защищенные модулем HSM ключи).

**Azure scheduler** - планировщик задач. Позволяет запускать задачи в облаке Azure.
Полностью выведен из эксплуатации 31 января 2022 г. и заменен На Azure Logic Apps.

**Azure Sentinel** - облачное решение для безопасности информации.
Предоставляет следующие возможности:

- SIEM
- Оркестрация, автоматизация и реагирование системы безопасности (SOAR)

### Сопоставление сервисов между разными провайдерами

В таблице ниже представлено сопоставление сервисов между разными провайдерами.

| Service Usage Type                                | Meter Category                | Meter Sub-Category        | Meter Name                   | Consumed Service              | Yandex analog                         | Additional info |
|---------------------------------------------------|-------------------------------|---------------------------|------------------------------|-------------------------------|---------------------------------------|-----------------|
| Standart tier of Analysis Services tabular model  | Analysis Services             | Tabular                   | Standard S%                  | Microsoft.AnalysisServices    | Yandex DataLens                       |                 |
| Basic tier of Analysis Services tabular model     | Analysis Services             | Tabular                   | Basic B%                     | Microsoft.AnalysisServices    | Yandex DataLens                       |                 |
| Developr tier of Analysis Services tabular model  | Analysis Services             | Tabular                   | Developer (Hours)            | Microsoft.AnalysisServices    | Yandex DataLens                       |                 |
| Basic tier of Analysis Services                   | Azure Analysis Services       | Basic                     | B%                           | Microsoft.AnalysisServices    | Yandex DataLens                       |                 |
| Developer tier of Analysis Services               | Azure Analysis Services       | Developer                 | Developer                    | Microsoft.AnalysisServices    | Yandex DataLens                       |                 |
| Standart tier of Analysis Services                | Azure Analysis Services       | Standard                  | S%                           | Microsoft.AnalysisServices    | Yandex DataLens                       |                 |
| Data transfer in Self gosted IR                   | Azure Data Factory            | v2                        | Data Movement Self Hosted IR | Microsoft.DataFactory         | Yandex Data Streams                   |                 |
| Data Orchestrarion in Self Hosted IR              | Azure Data Factory            | v2                        | Orchestration Self Hosted IR | Microsoft.DataFactory         | Yandex Data Streams                   |                 |
| Azure Data Factory Usage                          | Azure Data Factory            | v2                        | %                            | Microsoft.DataFactory         | Yandex Data Streams                   |                 |
| Data transfer in cloud IR                         | Azure Data Factory            | v2                        | Data Movement Cloud IR       | Microsoft.DataFactory         | Yandex Data Streams                   |                 |
| Data Orchestrarion in Self Hosted IR              | Azure Data Factory            | v2                        | Orchestration Cloud IR       | Microsoft.DataFactory         | Yandex Data Streams                   |                 |
| SQL Server Integration Services Standard          | Azure Data Factory            | v2                        | SSIS STD D4 v2               | Microsoft.DataFactory         | Yandex Data Streams                   |                 |
| -                                                 | Azure Database for PostgreSQL | Microsoft.DBforMyQL       |                              |                               | Yandex Managed Service for MySQL      |                 |
| -                                                 | Azure Database for PostgreSQL | Microsoft.DBforPostgreSQL |                              |                               | Yandex Managed Service for PostgreSQL |                 |
| Data Movement Cloud                               | Business Analytics            | Data Factory              | Data Movement Cloud          | Microsoft.DataFactory         | Yandex Data Lens                      |
| Data Movement On Premises                         | Business Analytics            | Data Factory              | Data Movement On Premises    | Microsoft.DataFactory         | Yandex Data Lens                      |
| -                                                 | Cache                         | Azure Redis Cache         | Microsoft.Cache              |                               | Yandex Managed Service for Redis      |                 |
| C% tier if cache                                  | Redis Cache                   |                           | C%                           | Microsoft.Cache               | Yandex Managed Service for Redis      |
| Standart or Basic C% tier                         | Redis Cache                   |                           | ___C%                        | Microsoft.Cache               | Yandex Managed Service for Redis      |
|                                                   | CDN                           | CDN                       | Standard CDN Data Transfer%  | Microsoft.Cdn                 | Yandex Cloud CDN                      |
| Standard CDN Data Transfer                        | Content Delivery Network      | Azure CDN%                | %Data Transfer               | Microsoft.Cdn                 | Yandex Cloud CDN                      |
| Reservation                                       | Cloud Services                | Reservation               | %License                     | Microsoft.Batch               |                                       |
| Entry-level VM usage                              | Cloud Services                | A%                        | Compute Hours                | Compute                       | Yandex Compute Cloud                  |
| General purpose VM usage                          | Cloud Services                | D%                        | Compute Hours                | Compute                       | Yandex Compute Cloud                  |
| Compute opimized VM usage                         | Cloud Services                | F%                        | Compute Hours                | Compute                       | Yandex Compute Cloud                  |
| Memory and storage optimized VM usage             | Cloud Services                | G%                        | Compute Hours                | Compute                       | Yandex Compute Cloud                  |
| High performance computing VM usage               | Cloud Services                | H%                        | Compute Hours                | Compute                       | Yandex Compute Cloud                  |
| GPU enabled VM usage                              | Cloud Services                | N%                        | Compute Hours                | Compute                       | Yandex Compute Cloud                  |
|                                                   | Data Box                      |                           |                              | Microsoft.DataBox             | -                                     |                 |
|                                                   | Key Vault                     |                           |                              | Microsoft.KeyVault            | Yandex Certificate Manager            |                 |
| Free Scheduler Units                              | Scheduler                     | Scheduler                 | Free Scheduler Units         |                               | -                                     |                 |
| Standard Scheduler Units                          | Scheduler                     | Standard Scheduler Units  |                              | -                             |                                       |                 |
| Free Unit                                         | Scheduler                     |                           | Free Unit                    | Microsoft.Scheduler           | -                                     |                 |
| Standard Unit                                     | Scheduler                     |                           | Standard Unit                | Microsoft.Scheduler           | -                                     |                 |
| Free Trial                                        | Sentinel                      |                           | Free Trial                   | microsoft.operationalinsights | -                                     |                 |
| Analysis                                          | Sentinel                      |                           | Analysis                     | microsoft.operationalinsights | -                                     |                 |

### Вывод

В ходе выполнения данной работы мы познакомились с облачными сервисами Azure. 
Также мы сопоставили сервисы Azure с сервисами Yandex Cloud.
Для большинства сервисов удалось найти аналоги в Yandex Cloud.
Поэтому можно сделать вывод, что возможно мигрировать на отечественные сервисы.