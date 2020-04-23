{% include_relative TableOfContents.md %}


# Code completion
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
