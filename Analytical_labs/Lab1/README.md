## Аналитическая работа 1 

### Цель работы

Знакомство с облачными сервисами. 
Понимание уровней абстракции над инфраструктурой в облаке. 
Формирование понимания типов потребления сервисов в сервисной-модели. 
Сопоставление сервисов между разными провайдерами. 
Оценка возможностей миграции на отечественные сервисы.

### Ход работы

### Классификация

Сервисы классифицированы согласно Apptio TBM Unified Model. 


### Список сервисов и их описание

Ниже представлены выданные нам сервисы и их описание.

**Amazon Redshift** - это облачный Data Warehouse. Используется для хранения и анализа больших 
объемов данных. Позволяет анализировать данные с помощью SQL и BI-инструментов. Ресурсы автоматически 
выделяются и масштабируются. Не взимается плата за неиспользуемые ресурсы. Основано на PostgreSQL, 
однако имеет ряд отличий. Например, в Redshift данные хранятся в столбцах, а не в строках, что позволяет
сократить время выполнения запросов. Так же, с целью повышения производительности,
вырезаны некоторые функции, такие как вторичные индексы. 

**AWS Directory Service** - сервис, предназначенный для интеграции с корпоративными директориями 
(Microsoft Active Directory или LDAP). Дает возможность удобного администрирования. 
Так же позволяет использовать другие сервисы AWS
с директориями, такие как Amazon WorkSpaces, Amazon WorkDoc и т.д.

**Amazon Glacier** - это сервис для хранения данных, которые не используются в течение длительного 
(архивации данных). Позволяет максимально дешево хранить данные по минимальной цене.
Пример использования: хранение архивов, резервных копий, мультимедиа, научных данных и т.д.
Предоставляет следующие типы хранилищ:
- S3 Glacier Instant Retrieval - для хранения данных, к которым нет необходимости 
часто обращаться. 
- S3 Glacier Flexible Retrieval - для хранения данных, к которым так же не требуется
часто обращаться, но при этом периодически надо извлекать огромные объемы. 
- S3 Glacier Deep Archive - самый дешевый вариант хранилища. Предназначен для 
архивных данных длительного хранения, доступ к которым требуется не чаще раза 
в год и может выполняться в асинхронном режиме.

**Amazon S3** - облачное хранилище данных. Позволяет хранить любые данные любого размера.
Данные хранятся в бакетах. Доступ к данным можно получить через API или консоль AWS.
Предоставляет высокую доступность, надежность, производительность и масштабируемость.
Может использовать для Web приложение, data lakes, мобильных приложений и т.д.
Имеются различные типы хранилищ, различающиеся по цене и доступности.

**Amazon SNS** - сервис для управления и доставки уведомлений. 
Использует два метода отправки сообщений:
- A2A - обеспечивает высокую пропускную способность для обмена push уведомлениями
между распределенными системами, микросервисами и бессерверными приложениями 
- A2P - обеспечивает доставку сообщений в виде SMS, электронной почты и push уведомлений

**Amazon translate** - сервис машинного перевода. Позволяет переводить тексты и речь.
представляет собой вариант автоматизации языкового перевода с использованием модели глубокого обучения.

**Amazon transcribe** - сервис автоматического распознавания речи. Позволяет преобразовывать
аудио в текст. использует передовые технологии машинного обучения для распознавания речи и преобразования ее в текст, 
что обеспечивает возможность эффективной обработки больших объемов аудиоданных.

**AWSCodePipeline** - сервис для непрерывной доставки и непрерывного развертывания.
 Позволяет автоматизировать работу конвейеров выпуска для быстрого и 
надежного обновления приложений и инфраструктуры.

**AWS CodeBuild** - сервис для компиляции кода. 
Позволяет компилировать код, выполнять тесты и создавать пакеты программного обеспечения.
Может использоваться для создания исходного кода с размещением на Github или 
как часть Ci/Cd

**Amazon Ml** - сервис машинного обучения. Позволяет создавать модели машинного обучения

**Amazon Polly** - сервис синтеза речи. Использует технологии глубокого обучения для
чтобы можно было преобразовать статьи в речь. Доступно большое количество языков и голосов.

### Сопоставление сервисов AWS и Yandex Cloud

Amazon Redshift - Yandex Query

AWS Directory Service - None

Amazon Glacier - Yandex Object Storage (не совсем, но близко)

Amazon S3 - Yandex Object Storage

Amazon SNS - None (Частично yandex message queue, это это скорее замена AWS SQS)

Amazon translate - Yandex Translate

Amazon transcribe - Yandex SpeechKit

AWSCodePipeline - None

AWS CodeBuild - None

Amazon Ml - Yandex DataSphere

Amazon Polly - Yandex SpeechKit

### Таблица

| Service Usage Type                                                                                       | Product Code        | Usage Type               | [lineItem/Operation] | lineItem/LineItemDescription |   |   | Yandex Cloud          |   |
|----------------------------------------------------------------------------------------------------------|---------------------|--------------------------|----------------------|------------------------------|---|---|-----------------------|---|
| Store data on SSDs. Scales automatically                                                                 | AmazonRedshift      | %Node:ra%                |                      |                              |   |   | Yandex Query          |   |
| Store data on different types of nodes. Automatically manage data placement across tiers of storage.     | AmazonRedshift      | %RMS%                    |                      |                              |   |   | Yandex Query          |   |
| Analyze all data                                                                                         | AmazonRedshift      | %DataScanned%            |                      |                              |   |   | Yandex Query          |   |
| Store data on SSDs                                                                                       | AmazonRedshift      | %Node:dc%                |                      |                              |   |   | Yandex Query          |   |
| Store data on HDDs                                                                                       | AmazonRedshift      | %Node:ds%                |                      |                              |   |   | Yandex Query          |   |
| Tax                                                                                                      | AWSDirectoryService |                          |                      | Tax%                         |   |   |                       |   |
| Microsoft Active Directory usage                                                                         | AWSDirectoryService | %MicrosoftAD-DC-Usage    |                      |                              |   |   | None                  |   |
| Simple Active Directory usage                                                                            | AWSDirectoryService | %SimpleAD-Usage          |                      |                              |   |   | None                  |   |
| Small Active Directory usage                                                                             | AWSDirectoryService | %Small-Directory-Usage   |                      |                              |   |   | None                  |   |
| Large Active Directory usage                                                                             | AWSDirectoryService | %Large-ADConnector-Usage |                      |                              |   |   | None                  |   |
| Provisioned capacity units                                                                               | AmazonGlacier       | %ProvisionedCapacityUnit |                      |                              |   |   | Yandex Object Storage |   |
| The number of GB-hours that data was stored in S3 Glacier                                                | AmazonGlacier       | %TimedStorage-ByteHrs    |                      |                              |   |   | Yandex Object Storage |   |
| lifecycle requests to S3 Glacier restore requests                                                        | AmazonGlacier       | %Requests-Tier3          |                      |                              |   |   | Yandex Object Storage |   |
| PUT, COPY, or POST requests plus LIST requests for all buckets and objects                               | AmazonGlacier       | %Requests-Tier1          |                      |                              |   |   | Yandex Object Storage |   |
| Prorated storage usage for objects deleted before the minimum commitment ended                           | AmazonGlacier       | %EarlyDelete%            |                      |                              |   |   | Yandex Object Storage |   |
| Prorated storage usage for objects deleted from Glacier Deep Archive before the minimum commitment ended | AmazonS3            | %EarlyDelete-GDA         |                      |                              |   |   | Yandex Object Storage |   |
| Prorated storage usage for objects deleted before the minimum commitment ended                           | AmazonS3            | %EarlyDelete-INT         |                      |                              |   |   | Yandex Object Storage |   |
| Prorated storage usage for objects deleted from Zone IA before the minimum commitment ended              | AmazonS3            | %EarlyDelete-ZIA%        |                      |                              |   |   | Yandex Object Storage |   |
| Prorated storage usage for objects deleted from Standart-IA before the minimum commitment ended          | AmazonS3            | %EarlyDelete-SIA%        |                      |                              |   |   | Yandex Object Storage |   |
| PUT, COPY, POST, or LIST requests                                                                        | AmazonS3            | %Requests%Tier1          |                      |                              |   |   | Yandex Object Storage |   |
| GET and HEAD requests                                                                                    | AmazonS3            | %Requests%Tier2          |                      |                              |   |   | Yandex Object Storage |   |
| Restore requests                                                                                         | AmazonS3            | %Requests%Tier3          |                      |                              |   |   | Yandex Object Storage |   |
| Lifecycle transition                                                                                     | AmazonS3            | %Requests%Tier4          |                      |                              |   |   | Yandex Object Storage |   |
| Bulk restore requests                                                                                    | AmazonS3            | %Requests%Tier5          |                      |                              |   |   | Yandex Object Storage |   |
| Expedited restore requests                                                                               | AmazonS3            | %Requests%Tier6          |                      |                              |   |   | Yandex Object Storage |   |
| Total of tags on all objects in the bucket                                                               | AmazonS3            | %TagStorage-TagHrs%      |                      |                              |   |   | Yandex Object Storage |   |
| Delivery via HTTP                                                                                        | AmazonSNS           | %DeliveryAttempts-HTTP   |                      |                              |   |   | None                  |   |
| Delivery via SQS                                                                                         | AmazonSNS           | %DeliveryAttempts-SQS    |                      |                              |   |   | None                  |   |
| Price per SMS                                                                                            | AmazonSNS           | %SMS-Price%              |                      |                              |   |   | None                  |   |
| Sent messages count                                                                                      | AmazonSNS           | %SMS-Sent%               |                      |                              |   |   | None                  |   |
| Delivery via APN                                                                                         | AmazonSNS           | %DeliveryAttempts-APNS%  |                      |                              |   |   | None                  |   |
| Translated text                                                                                          | translate           | %TranslateText           |                      |                              |   |   | Yandex Translate      |   |
| Streamed audio                                                                                           | transcribe          | %StreamingAudio          | %StreamingAudio      |                              |   |   | Yandex SpeechKit      |   |
| Transcribed Audio                                                                                        | transcribe          | %TranscribeAudio         | TranscribeAudio      |                              |   |   | Yandex Translate      |   |
| Tax                                                                                                      | AWSCodePipeline     |                          |                      | Tax%                         |   |   |                       |   |
| Trial pipelines                                                                                          | AWSCodePipeline     | %trialPipeline%          |                      |                              |   |   | None                  |   |
| Code Build usage                                                                                         | CodeBuild           |                          |                      |                              |   |   |                       |   |
| Amazon ML model training in box                                                                          | AmazonML            | %AMLBoxUsage             | TrainModel           |                              |   |   | Yandex DataSphere     |   |
| Amazon ML model evaluating in box                                                                        | AmazonML            | %AMLBoxUsage             | EvaluateModel        |                              |   |   | Yandex DataSphere     |   |
| Amazon Polly Usage                                                                                       | AmazonPolly         |                          |                      |                              |   |   | Yandex Translate      |   |

### Вывод

В ходе выполнения данной работы мы ознакомились с облачными сервисами от Amazon. 
Кроме того, мы сопоставили сервисы AWS и Yandex Cloud. Не для всех сервисов получилось найти
аналоги в Yandex Cloud. Например, AWS Directory Service, AWS CodeBuild, AWS CodePipeline. Для
некоторых сервисов удалось найти аналоги, но они могли не полностью совпадать. 
Например, Amazon Glacier. В целом, можно сказать, что основные сервисы AWS имеют аналоги в 
Yandex Cloud, что делает миграцию возможной, если нет необходимости в использовании
узконаправленных сервисов.