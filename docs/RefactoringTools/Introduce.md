---
parent: Refactoring Tools
nav_order: 4
---

# Refactor: Introduce

Невероятно полезная группа инструментов рефакторинга. Содержит 4 инструмента со схожей логикой работы: вынести expression в переменную/константу/свойство/параметр. Особенно полезен вынос в переменную.

Стандартные шорткаты довольно легко запомнить - `Ctrl+Alt+Первая буква операции`:
- Introduce **V**ariable - `Ctrl+Alt+V`
- Introduce **C**onstant - `Ctrl+Alt+C`
- Introduce **F**ield - `Ctrl+Alt+F`
- Introduce **P**arameter - `Ctrl+Alt+P`

![Introduce example](assets/Introduce.gif)

На этой гифке также продемонстрирована работа инструмента `Extract Method` (шорткат `Ctrl+Atl+M`). Он довольно близок к Introduce, по логике своей работы. Умеет выносить произвольные участки кода в методы и определять аргументы создаваемого метода. Вам остается только поправить название и задать return type, хотя и это PhpStorm попытается угадать. :smile:

<br>

Также есть обратная `Introduce` операция - `Inline`.
![Introduce example](assets/Inline.gif)
