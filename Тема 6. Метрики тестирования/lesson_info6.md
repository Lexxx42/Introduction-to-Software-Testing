# Модуль 6. Метрики тестирования

## Как измерить результаты тестирования?

Давайте представим всё количество созданных на проекте тестов. Ранее мы поняли,
что «качество» - это метрика того, насколько наш продукт соответствует ожиданиям. Как
следствие, мы можем предположить, что качество – это количество успешно выполненных
тестов.

При этом, важно понимать, что количество выполненных тестов на практике часто
оказывается меньше количества созданных тестов. Среди выполненных тестов есть
определенное количество выполненных успешно и неуспешно. Помимо этого, количество
созданных тестов во многих проектах бывает меньше запланированного («задуманного»)
количества тестов.

**Мы будем определять качество как произведение:**

```
(Созданные тесты) x (Выполненные тесты) x (Прошедшие тесты)
```

При условии, что каждый из множителей – относительная величина со значением от
нуля до единицы, мы заметим, что значение качества будет сильно меньше единицы.

## Матрица отслеживания (Traceability matrix, матрица трассируемости)

Матрица представляет собой таблицу, в которой проставлено соотношение между
требованиями и тестами. Далее для каждого из требований отмечаются тесты, которые это
требование покрывают. Некоторые тесты также могут покрывать несколько требований
(что в индустрии иногда встречается, хотя не считается хорошей практикой). По итогам
составления матрицы, а также занесения в неё результатов выполнения тестов, становится
понятно:

+ Насколько каждое требование покрыто тестами;
+ Насколько требование эффективно тестируется;
+ Какой объем усилий потребуется для проверки того или иного требования;
+ Какие результаты тестирования связаны с тем или иным требованием;
+ Насколько то или иное требование готово;
+ Насколько то или иное требование реализуемо.

## Отслеживание тестирования во времени

Вспомним возможные состояния тестов: созданные, запланированные, успешно
выполненные и неуспешно выполненные. Успешно и неуспешно выполненные тесты
можно назвать «выполненными», запланированные, но еще не выполненные можно назвать
«невыполненными». На основании этих терминов, можно сформулировать следующие
метрики:

`Run rate = (выполненные)/(запланированные)`

`Pass rate = (успешно выполненные)/(выполненные)`

Целевое значение pass rate крайне редко бывает равным 100%, обычно это величина
чуть меньше (например, 97%).

Обе эти метрики начинают иметь смысл при измерении на длительном промежутке
времени. Значение показателей в какой-то конкретный момент времени не может дать
внятной информации о качестве продукта, скорости работы команды или потенциальных
достижениях. Обычно значения метрик собирают с определенным интервалом, а для
удобной их визуализации используются графики.

Часто `run rate` и `pass rate` изображают на одном графике, на котором также явным
образом изображают значение дедлайна, от которого отмечают убывание времени для того,
чтобы наглядно демонстрировать, насколько команда продвигается к заявленным
показателям. Графическое представление `run rate` часто имеет вид S-кривой: вначале
результатов мало, затем, на серединном участке проекта наблюдается рост значений, а по
мере приближения к концу проекта рост вновь замедляется. Формулу для S-кривой вы
можете посмотреть в слайдах презентации к этому модулю.

## Дополнительные метрики тестирования

`Плотность дефектов = (количество дефектов)/(объем кода)`

`Отклоненные дефекты = (отклоненные дефекты)/(дефекты)`

`Плотность покрытия = (тесты)/(требования)`

`Доля переоткрытых дефектов = (переоткрытые)/(дефекты)`

Переоткрыте дефекты – те дефекты, которые разработчики считали исправленными,
но на самом деле они исправленными не оказались.

Все четыре метрики позволяют оценивать и прогнозировать работы по выявлению
дефектов и их исправлению.

`«Сила» тестов = ((дефект)/(тест))/(дефекты/тесты)`

Это отношение условно показывает, сколько дефектов помогает найти один тест.
Такая метрика позволяет оценить эффективность тест-дизайна.

## Как использовать метрики?

+ **Метрики должны что-то означать.** Если метрика ничего не значит, не стоит её
  использовать.
+ **Метрики должны быть простыми.** Чем проще метрики, тем лучше их понимают
  все участники процесса.
+ **Действительно отслеживать и действительно использовать.** Иначе работа с
  метриками превратится в рутину, которая никому не приносит удовольствия и
  пользы. 
