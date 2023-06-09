# Глоссарий к теме 2

В соответствии с: https://habr.com/ru/post/549054/

## Классификация тестирования по доступу к коду

+ Тестирование белого ящика — метод тестирования ПО, который предполагает полный доступ к коду проекта.

+ Тестирование серого ящика — метод тестирования ПО, который предполагает частичный доступ к коду проекта (комбинация
  White Box и Black Box методов).

+ Тестирование чёрного ящика — метод тестирования ПО, который не предполагает доступа (полного или частичного) к
  системе.
  Основывается на работе исключительно с внешним интерфейсом тестируемой системы.

## Классификация тестирования по уровню детализации приложения

+ Модульное тестирование — проводится для тестирования какого-либо одного логически выделенного и изолированного
  элемента (модуля) системы в коде. Проводится самими разработчиками, так как предполагает полный доступ к коду.

+ Интеграционное тестирование — тестирование, направленное на проверку корректности взаимодействия нескольких модулей,
  объединенных в единое целое.

+ Системное тестирование — процесс тестирования системы, на котором проводится не только функциональное тестирование, но
  и
  оценка характеристик качества системы — ее устойчивости, надежности, безопасности и производительности.

+ Приёмочное тестирование — проверяет соответствие системы потребностям, требованиям и бизнес-процессам пользователя.

+ Сквозное тестирование (end-to-end testing) — тип тестирования программного обеспечения, который проверяет программную
  систему вместе с ее интеграцией с внешними интерфейсами.

## Классификация тестирования по объекту тестирования

+ Функциональное тестирование (functional testing) — направлено на проверку корректности работы функциональности
  приложения

+ Нефункциональное тестирование (non-functional testing) — тестирование атрибутов компонента или системы, не относящихся
  к
  функциональности.

+ Тестирование производительности (performance testing) — определение стабильности и потребления ресурсов в условиях
  различных сценариев использования и нагрузок.

+ Нагрузочное тестирование (load testing) — определение или сбор показателей производительности и времени отклика
  программно-технической системы или устройства в ответ на внешний запрос с целью установления соответствия требованиям,
  предъявляемым к данной системе (устройству).

+ Стрессовое тестирование (stress testing) — тип тестирования направленный для проверки, как система обращается с
  нарастающей нагрузкой (количеством одновременных пользователей).

+ Тестирование интерфейса (GUI/UI testing) — проверка требований к пользовательскому интерфейсу.

+ Тестирование удобства использования (usability testing) — это метод тестирования, направленный на установление степени
  удобства использования, понятности и привлекательности для пользователей разрабатываемого продукта в контексте
  заданных
  условий.

+ Тестирование локализации (localization testing) — проверка адаптации программного обеспечения для определенной
  аудитории
  в соответствии с ее культурными особенностями.

+ Тестирование безопасности (security testing) — это стратегия тестирования, используемая для проверки безопасности
  системы, а также для анализа рисков, связанных с обеспечением целостного подхода к защите приложения, атак хакеров,
  вирусов, несанкционированного доступа к конфиденциальным данным.

+ Тестирование надёжности (reliability testing) — один из видов нефункционального тестирования ПО, целью которого
  является
  проверка работоспособности приложения при длительном тестировании с ожидаемым уровнем нагрузки.

+ Тестирование совместимости (англ. compatibility testing) — вид нефункционального тестирования, основной целью которого
  является проверка корректной работы продукта в определенном окружении, включая аппаратные платформы, операционные
  системы, браузеры, различные расширения экрана и т.д. (в соответствии
  с https://qasquad.com/en/blog/testirovanie-sovmestimosty)

+ Конфигурационное тестирование (англ. Configuration testing) - вид нефункционального тестирования, которые определяет,
  как продукт будет работать в условиях смены конфигурации (платформы, драйверов и т.д.). При конфигурационном
  тестировании тестируют различные конфигурации железа, софта, которые поддерживает система. Например, сайт по ТЗ должен
  работать на веб-браузерах Google Chrome, Mozilla Firefox и Apple Safari. Или приложение должно запускаться с 500 мб
  оперативной памяти. Тестирование совместимости проверяет совместимость с объектами вне зависимости от того
  поддерживает
  ли их система (в соответствии
  с https://vk.com/@zapiskisedogotestera-vidy-testirovaniya-po-celyam-vidy-nefunkcionalnogo-testirov2). 