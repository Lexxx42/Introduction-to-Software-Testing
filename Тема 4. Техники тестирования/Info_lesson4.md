# Модуль 4. Техники тестирования

## Позитивное и негативное тестирование

**Позитивное тестирование** фокусируется на тех параметрах и их значениях,
которые система должна принимать в качестве корректных и корректно их обрабатывать.
Проверяется то, что система принимает такие параметры и выдает корректный результат.

При **негативном тестировании**, наоборот, проверяется то, что система не
принимает те параметры, которые она не должна принимать. Выполняется проверка того,
что система корректно уходит в отказ: возвращает правильно все сообщения об ошибках,
правильно отображает все окна и, прежде всего, не принимает неправильные параметры.

## Классы эквивалентности и анализ граничных значений

Разберем эту технику на примере. Представим систему регистрации с полем ввода
пароля. Гипотетически мы можем перебирать все возможные пароли для того, чтобы
проверить, что система корректно работает. В реальности инженерам хотелось бы
минимизировать количество проверяемых значений, получая результаты близкого по
уровню к перебору «всех» значений качества.

Суть предлагаемой техники сводится к тому, что вся область допустимых значений
разбивается на несколько классов с одинаковым поведением – классов эквивалентности.
Для создания тест-кейсов используют следующие значения:

+ Чуть меньше минимума (минимально допустимого корректного значения).
  Проверяется корректный отказ системы.
+ Минимум. Проверяется корректное поведение системы (отсутствие ухода в два
  состояния одновременно).
+ Чуть больше минимума. Проверка того, что система корректно обрабатывает
  введённое значение.
+ Номинальное значение («середина» диапазона). Проверка того, что система
  корректно обрабатывает введённое значение.
+ Чуть меньше максимума. Проверка того, что система корректно обрабатывает
  введённое значение.
+ Максимум. Проверяется корректное поведение системы (отсутствие ухода в два
  состояния одновременно).
+ Чуть больше максимума (максимально допустимого корректного значения).
  Проверяется корректный отказ системы.

Такой дизайн системы позволяет нам предположить, что во всех классах
эквивалентности система будет корректно принимать (или не принимать), а также
обрабатывать корректные значения (или уходить в отказ).

Стоит отметить, что одни и те же тест-кейсы могут работать с различными данными.
Поэтому, в тест-менеджмент системах данные часто рассматриваются отдельно. В таком
случае при описании данных в тест-кейсе используются не конкретные данные, а ссылка на
набор, тем самым тест-кейс разбивается на набор действий и набор данных. Такой подход
упрощает работу с редактированием тестов – мы можем вносить изменения только в
действия или только в данные, оставляя другие компоненты неизменными.

Представим форму пароля, которая может принимать входные значения длиной от
шести до десяти символов. Для тестирования работоспособности формы нам доступны:

+ **Набор действий**: введение пароля, нажатие кнопки «ввод»;
+ **Набор данных**, созданный на основе классов эквивалентности:
    + Чуть меньше минимума – 5 символов.
    + Минимум - 6 символов.
    + Чуть больше минимума – 7 символов
    + Номинальное значение – 8 символов
    + Чуть меньше максимума – 9 символов
    + Максимум – 10 символов
    + Чуть больше максимума - 11 символов

## Таблица принятия решений

К более продвинутым техникам относится таблица принятия решений, пришедшая в
тестирование из управления и бизнес-аналитики.

Таблица решений состоит из:

+ Вариантов условий, создаваемых тестом для системы;
+ Вариантов выполнения действий системой в зависимости от созданных
  условий;
+ Комбинаций создаваемых условий;
+ Комбинаций необходимых реакций системы на создаваемые условия.

Рассмотрим пример формы для ввода имени пользователя и пароля:

+ Варианты условий, создаваемых тестом для системы:
    + Введено имя пользователя;
    + Введено имя администратора;
    + Введен верный пароль;
    + Введен неверный пароль.

+ Варианты выполнения действий системой в зависимости от созданных
  условий
    + Выполнена авторизация;
    + Демонстрируется статистика для администратора;
    + Демонстрируется сообщение об ошибке авторизации

+ Комбинации создаваемых условий и комбинации необходимых реакций
  системы на создаваемые условия (примеры):

    + Для верно введенного имени обычного пользователя и верного
      пароля выполняется авторизация и не выполняются показ
      статистики и сообщения об ошибке;
    + Для верно введенного имени администратора и верного
      пароля выполняются авторизация и показ статистики и не
      демонстрируется сообщение об ошибке;
    + Для верно введенного имени пользователя и неверно
      введенного пароля не выполняется авторизация, не
      демонстрируется статистика, при этом показывается
      сообщение об ошибке.

В такой таблице должно быть 16 столбцов (4 условия, варианты выполнения «Да»
или «Нет» для каждого из них, все возможные их сочетания). Использование таблицы
позволяет нам выполнить следующую важную часть тест-дизайна: **выделить те
комбинации условий, которые производят одинаковые наборы действий со стороны
системы.** Например, в нашей таблице реакция системы на отсутствие введенного пароля
(условие N для верного и неверного паролей) одинакова как для верного имени обычного
пользователя, так и для верного имени администратора. Аналогично при верно введенном
имени пользователя и неверном пароле реакция системы (сообщение об ошибке) будет
такой же, как при верно введенном имени администратора и неверном пароле. Таким
образом, мы можем сократить количество тест-кейсов для системы как минимум на два:
если поле пароля пустое, то нам не важно, какой пользователь авторизуется в системе, если
введен неверный пароль, то нам неважно, какой именно пользователь авторизуется.

## Предугадывание ошибок

Этот подход предполагает интуитивные попытки угадать, какие ошибки заложены в
коде. Часто он зависит от опыта инженера по тестированию. На начальных этапах проекта
такой подход может работать, позволяя находить распространенные ошибки, которые
известны опытным тестировщикам. При этом, тестирование методом предугадывания
ошибок является неповторимым процессом и не рекомендуется при выходе проекта из
начальной стадии.

## Оформление дефектов (bug reporting)

Рассмотрим, какие поля могут включаться в оформление дефекта:

+ Имя или другой идентификатор того человека, который завел дефект в
систему
+ Название продукта, в котором был обнаружен дефект
+ Версия продукта
+ Компонент продукта
+ Аппаратная платформа («железо»)
+ Операционная система
+ Priority
+ Severity
+ Краткое описание
+ Развернутое описание, включающее следующие пункты:
  + Шаги для воспроизведения дефекта; 
  + Ожидаемый результат;
  + Наблюдаемый результат
