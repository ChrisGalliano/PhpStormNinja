---
parent: Refactoring Tools
nav_order: 4
---

# Refactor: Introduce

Одна из наиболее полезных групп инструментов. Содержит 4 инструмента со схожей логикой работы: вынести expression в переменную/константу/свойство/параметр. Особенно полезен вынос в переменную.

Стандартные шорткаты довольно легко запомнить - `Ctrl+Alt+Первая буква операции`:
- Introduce Variable - `Ctrl+Alt+V`
- Introduce Constant - `Ctrl+Alt+C`
- Introduce Field - `Ctrl+Alt+F`
- Introduce Parameter - `Ctrl+Alt+P`

![Introduce example](assets/Introduce.gif)

Кстати, на этой гифке также продемонстрирована работа инструмента `Extract Method` (шорткат `Ctrl+Atl+M`). Он умеет выносить куски кода любого размера и определять аргументы создаваемого метода. Вам остается только поправить название и задать return type, хотя он и это попытается угадать. :smile:

<br>

Также есть обратная `Introduce` операция - `Inline`.
![Introduce example](assets/Inline.gif)
