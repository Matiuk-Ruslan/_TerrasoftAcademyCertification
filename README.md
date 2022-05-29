# Package

Name|Version|Description
---|---|---
_TerrasoftAcademyCertification|v1.0.0|Инициализация пакета
_TerrasoftAcademyCertification|v1.1.0|Сущность, деталь, справочники, интерфейс, бизнес-правило и данные
_TerrasoftAcademyCertification|v1.2.0|Новые поля в объектах, валидация и расчет
_TerrasoftAcademyCertification|v1.3.0|Веб-сервис
_TerrasoftAcademyCertification|v1.4.0|Бизнес-процесс, публикация и подписка на сообщение, обновление детали

## Description

* **Package:** _TerrasoftAcademyCertification
  * **Version:** v1.0.0
    * Присвоение издателя
    * Присвоение версии
  * **Version:** v1.1.0
    * Создан объект `UsrRealtyType`
      * Создан справочник "Тип недвижимости"
      * Справочник привязан к пакету
      * Наполнение справочника привязано к пакету
    * Создан объект `UsrOfferTypeRealty`
      * Создан справочник "Тип предложения недвижимости"
      * Справочник привязан к пакету
      * Наполнение справочника привязано к пакету
    * Создан объект `UsrRealtyViews`
      * Добавлено поле [`UsrPotentialClient` / Потенциальный клиент]
      * Добавлено поле [`UsrResponsible` / Ответственный]
        * Значение по умолчанию [Текущий пользователь]
      * Добавлено поле [`UsrComment` / Комментарий]
      * Добавлено поле [`UsrRealty` / Недвижимость]
      * Добавлена деталь [`UsrRealtyViewsDetail` / Просмотры недвижимости]
      * Добавлена страница редактирования `UsrRealtyViewsPage`
      * Данные привязаны к пакету
    * Создан раздел [Недвижимость]
      * Создан объект [`UsrRealty` / Недвижимость]
        * Добавлено поле [`UsrRealtyType` / Тип]
        * Добавлено поле [`UsrOfferTypeRealty` / Тип предложения]
        * Добавлено поле [`UsrArea` / Площадь]
        * Добавлено поле [`UsrPrice` / Цена]
        * Добавлено поле [`UsrNotes` / Комментарий]
      * Добавлена реестр раздела [`UsrRealtySection` / Схема раздела: "Недвижимость"]
      * Добавлена страница редактирования [`UsrRealtyPage` / Страница редактирования: "Недвижимость"]
        * Добавленые поля выведены на UI
        * Добавлена вкладка [`TabBasicInformation` / Основная информация]
          * Добавлена деталь [`UsrRealtyViewsDetail` / Просмотры недвижимости]
        * Добавлено бизнес-правило [Комментарий: Делать поле обязательным]
      * Данные привязаны к пакету
  * **Version:** v1.2.0
    * Обновлен объект [`UsrRealty` / Недвижимость]
      * Добавлено поле [`UsrCommission` / Коммисия]
    * Обновлен объект [`UsrOfferTypeRealty` / Тип предложения недвижимости]
      * Добавлено поле [`UsrCommissionRate` / Комиссионная ставка]
      * Значение по умолчанию [0]
    * Логика страницы редактирования [`UsrRealtyPage` / Страница редактирования: "Недвижимость"]
      * Валидация поля [`UsrArea` / Площадь]
      * Валидация поля [`UsrPrice` / Цена]
      * Расчет комиссии [`UsrCommission` / Коммисия]
  * **Version:** v1.3.0
    * Реализован веб-сервис `DataService`
      * Endpoint: `{{siteAddress}}/0/rest/DataService/GetTotalPrice`
  * **Version:** v1.4.0
    * Обновлен бизнес-процесс `UsrAutomaticCreationOfRecords`
      * Добавлена логика публикации сообщения по `WebSocket`
    * Замещен модуль `ClientMessageBridge`
      * Реализована рассылка сообщения `SetRealtyViews` внутри приложения
    * Обновлен клиентский модуль `UsrRealtyPage`
      * Реализована подписка на сообщение `SetRealtyViews`
      * Добавлен метод обновления детали `UsrRealtyViewsDetail`
