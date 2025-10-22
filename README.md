# Распознавание неформализованных документов электронного обмена
Репозиторий с шаблоном разработки «Распознавание неформализованных документов электронного обмена».

## Описание
Решение позволяет:
Добавлять блок типа скрипт «Распознавание неформализованных документов электронного обмена», с помощью которого неформализованные документы, поступившие из сервиса электронного обмена Диадок, будут автоматически интеллектуально обрабатываться сервисами Ario.
<img width="828" height="602" alt="image" src="https://github.com/user-attachments/assets/10398d0e-0758-408a-89b3-3e579f91d1d1" />

Состав объектов разработки:
1.	Перекрытие модуля «Интеллектуальная обработка» (SmartProcessing).
2.	Блок типа Скрипт «Распознавание неформализованных документов эл. обмена.»
3.	Перекрытие справочника «Бинарные образы документов» (Blob). 
4.	Заказное свойство ExistingDocId в перекрытии справочника «Бинарные образы документов» (Blob). 
5.	Константа ElectronicLineText.
6.	Переопределенные функции:
   6.1.	 CreateSupAgreement;
   6.2.	 CreateWaybill;
   6.3.  CreateUniversalTransferDocument;
   6.4.  CreateUniversalTransferCorrectionDocument;
   6.5.  CreateTaxInvoice;
   6.6.  CreateTaxInvoiceCorrection;
   6.7.  CreateSimpleDocument;
   6.8.  CreateIncomingLetter;
   6.9.  CreateIncomingInvoice;
   6.10. CreateContractStatement;
   6.11. CreateContract.
7.	Функции:
   7.1.  ProcessToArio;
   7.2.  FillingDocumentCardsInArio;
   7.3.  ProcessPackageInArioS.
8.	Копии функций базового слоя:
   8.1.	 ProcessCapturedPackage;
   8.2.	 GetArioConnector.


> [!NOTE]
> Замечания и пожеланию по развитию шаблона разработки фиксируйте через [Issues](https://github.com/DirectumCompany/rx-template-smart-processing-nonformalized-doc/issues).
При оформлении ошибки, опишите сценарий для воспроизведения. Для пожеланий приведите обоснование для описываемых изменений - частоту использования, бизнес-ценность, риски и/или эффект от реализации.
> 
> Внимание! Изменения будут вноситься только в новые версии.

## Варианты расширения функциональности на проектах
1.	Использовать блок в любых типах задач. Для реализации необходимо обязательно добавить приведение _obj к типу задачи, в рамках схемы которой, будет добавлен блок. Приведение добавляется на событии «Выполнение» блока Скрипт «Распознавание неформализованных документов эл. обмена.»
2.	Изменить логику создания документов после обработки в переопределениях функций CreateSupAgreement, CreateWaybill, CreateUniversalTransferDocument, CreateUniversalTransferCorrectionDocument, CreateTaxInvoice, CreateTaxInvoiceCorrection, CreateSimpleDocument, CreateIncomingLetter, CreateIncomingInvoice, CreateContractStatement, CreateContract.
3.	Изменить логику отправки на верификатора в функции ProcessCapturedPackage.

## Порядок установки
Для работы требуется установленный Directum RX версии 4.12 и выше.

## Установка для ознакомления
1. Склонировать репозиторий с rx-template-smart-processing-nonformalized-doc в папку.
2. Указать в config.yml в разделе DevelopmentStudio:
```xml
   GIT_ROOT_DIRECTORY: '<Папка из п.1>'
   REPOSITORIES:
      repository:
      \-   '@folderName': 'work'
          '@solutionType': 'Work'
          '@url': https://github.com/DirectumCompany/rx-template-approval-from-registry'
      \-   '@folderName': 'base'
          '@solutionType': 'Base'
          '@url': ''
```

## Установка для использования на проекте
Возможные варианты

**A. Fork репозитория**
1. Сделать fork репозитория rx-template-smart-processing-nonformalized-doc для своей учетной записи.
2. Склонировать созданный в п. 1 репозиторий в папку.
3. Указать в config.yml в разделе DevelopmentStudio:
```xml
   GIT_ROOT_DIRECTORY: '<Папка из п.1>'
   REPOSITORIES:
      repository:
      \-   '@folderName': 'work'
          '@solutionType': 'Work'
          '@url': https://github.com/DirectumCompany/rx-template-approval-from-registry'
      \-   '@folderName': 'base'
          '@solutionType': 'Base'
          '@url': ''
```

**B. Подключение на базовый слой.**
Вариант не рекомендуется, так как при выходе версии шаблона разработки не гарантируется обратная совместимость.
1. Склонировать репозиторий rx-template-smart-processing-nonformalized-doc в папку.
2. Указать в config.yml в разделе DevelopmentStudio:
```xml
   GIT_ROOT_DIRECTORY: '<Папка из п.1>'
   REPOSITORIES:
      repository:
      \-   '@folderName': 'work'
          '@solutionType': 'Work'
          '@url': https://github.com/DirectumCompany/rx-template-approval-from-registry'
      \-   '@folderName': 'base'
          '@solutionType': 'Base'
          '@url': ''
```

**C. Копирование репозитория в систему контроля версий.**
Рекомендуемый вариант для проектов внедрения.
1. В системе контроля версий с поддержкой git создать новый репозиторий.
2. Склонировать репозиторий <Название репозитория> в папку с ключом `--mirror`.
3. Перейти в папку из п. 2.
4. Импортировать клонированный репозиторий в систему контроля версий командой:
`git push –mirror <Адрес репозитория из п. 1>`

