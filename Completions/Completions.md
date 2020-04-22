# Completions
```php
# @todo basic description & terminology 
```
- [Auto-Completion](#auto-completion)
- [Live templates](#live-templates)
- [Other plugins](#other-plugins)


## Auto-Completion
Это классическое авто-дополнение кода при наборе названия
- класса
- метода
- переменной
- etc.

Обучаться чему-то хитрому при использовании авто-дополнения не нужно. Но можно подкрутить настройки PhpStorm для более комфортного использования.

Переходим в `Settings -> Editor -> General -> Code completion`

Первым делом снимаем галочку с `Match Case`, теперь при составлении авто-дополнений вообще не будет учитываться регистр.
![Case insensitivity example](/Completions/assets/CaseInsensitive.gif)

<br/>
<br/>

Также включаем `Automatically insert single suggestions for: - Smart Type Completion`

В PhpStorm есть 2 типа авто-дополнения, стандартный "Completion" (Ctrl+Space) и умный - "Smart Type Completion" (Ctrl+Shift+Space)

Smart Type Completion при составлении вариантов дополнения учитывает контекст. Например тип аргумента вызываемого метода:  
![Smart Type Completion example](/Completions/assets/SmartTypeCompletion.gif)

<br/>

При включении `Automatically insert single suggestions for: - Smart Type Completion` PhpStorm автоматически вставит вариант дополнения, при вызове Smart Type Completion, если существует только 1 подходящий вариант: 
![Smart Type Completion Insert example](/Completions/assets/SmartTypeCompletionInsert.gif)

<br/>
<br/>

Также советую включить `Machine Learning-Assisted Completion` для PHP. PhpStorm будет анализировать, какие варианты авто-дополнения вы выбираете чаще и поднимать их повыше в списке.

<br/>

Вот так выглядят мои настройки на текущий момент (PhpStorm 2020.1)
![Screenshot of my settings](/Completions/assets/CodeCompletionSettings.png)


## Live templates
Во время разработки мы часто печатаем стандартные, повторяющиеся структуры, с небольшими отличиями: циклы, if-ы, объявляем методы, бросаем исключения и т.д. <br/>
Live templates позволяет автоматизировать создание этих структур.

В PhpStorm есть ряд стандартных live темплейтов, давайте рассмотрим один для примера, переходим в<br/> 
Settings -> Editor -> Live Templates -> PHP -> fore
![Screenshot of "fore" Live Template](/Completions/assets/LiveTemplateFore.png)

<br/>

Поле | Описание
---- | --------
`Abbreviation` | сокращение нашего темплейта, по сути шорткат, по которому он вызывается
`Description` | описание темплейта (отображается рядом с аббревиатурой в списке темплейтов и при выводе в списке completions)
`Template text` | собственно сам темплейт
`Options: expand with` | "горячая клавиша", при нажатии которой будет разворачиваться темплейт 
`Options: reformat according to style` | после разворачивания темплейта он будет отформатирован согласно вашим настройкам Code Style
`Applicable in *; statement. Chandge` | контекст, в котором этот темплейт может развернуться

И также у нас есть кнопка `Edit Variables`, ее мы рассмотрим позже

Итак, содержание темплейта `fore`:
```php
foreach ($ITERABLE$ as $VAR_VALUE$) {
    $END$
}
```   

`$ITERABLE$`, `$VAR_VALUE$` - это "пользовательские" переменные.<br/>
В процессе разворачивания темплейта каретка ввода будет поочередно подставляться на место каждой переменной. После того, как мы закончили ввод кода на месте переменной `$ITERABLE$` нужно нажать Enter или Tab и мы автоматически перейдем к заполнению следующей переменной - `$VAR_VALUE$`.

`$END$` - это стандартная переменная, она обозначает, что в этой точке нужно остановить каретку ввода, когда темплейт развернется:
![Screenshot of "fore" Live Template](/Completions/assets/ExpandForeLiveTemplate.gif)

<br/>

На гифке можно наблюдать еще одну особенность - массив `$users` мы выбираем вручную, а значение `$user`, на место `$VAR_VALUE$`, подставляется автоматически. Как это происходит?<br/>
Дело в настройках переменных, которые прячутся под кнопкой `Edit Variables`. Нажимаем на нее и видим следующее окно:<br/>
![Screenshot of "fore" Live Template](/Completions/assets/ForeLiveTemplateVariables.png)

Все пользовательские переменные добавляются в эту табличку автоматически. В табличке есть 4 колонки:

Название | Описание
-------- | -------------------
`NAME` | название переменной
`Expression` | спец. функция, которая будет применена к переменной. Их достаточно много, почитать про них можно [тут](https://www.jetbrains.com/help/phpstorm/template-variables.html#predefined_functions). На примере переменной `$VAR_VALUE$` можно увидеть, что для нее установлен expression `phpSuggestVariableName()`. Как нетрудно догадаться, именно благодаря этому PhpStorm пытается угадать название переменной. Важный нюанс, для работы `phpSuggestVariableName()` **дефолтное значение должно быть заполнено**.
`Default value` | Ничего особенного, но есть нюанс. Дефолтное значение также является выражением, которое может ссылаться на другой Live Template. Если ваше дефолтное значение - литерал, оно должно быть обернуто в двойные кавычки, напр. `"$item"`
`Skip if defined` | PhpStorm не будет останавливаться на месте этой переменной, если ее значение уже заполнено.

<br/>

Для примера, вот мой темплейт `fore` для HTML контекста
```php
<? foreach ($ITERABLE$ as $VAR_VALUE$) { ?>
    $END$
<? }?>
```
Настройки переменных идентичны оригинальному `fore`. Этот темплейт я использую для написания `foreach` во вьюшках.<br/>
Также для HTML контекста у меня есть темплейты для вызова глобальных функций перевода, экранирования, установки layout, разворачивания `if` и т.д. Это мощный инструмент, который ограничивается только вашей фантазией и желанием оптимизировать свой workflow. :nerd_face:



## Other Plugins
[deep-assoc-completion](https://plugins.jetbrains.com/plugin/9927-deep-assoc-completion) - комплитит ключи ассоциативных массивов