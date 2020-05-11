---
title: Macros
nav_order: 6
has_children: false
---
# Macros

Достаточно стандартный инструмент, позволяющий записать любой набор действий и повесить на них шорткат. Поочередно воспроизводит каждое действие. Иногда может тупить/ломаться, потому советую уделить большее внимание таким инструментам как [Live Templates]({{ site.baseurl }}{% link docs/Completions/LiveTemplates.md %}) и [Postfix Completion]({{ site.baseurl }}{% link docs/Completions/PostfixCompletion.md %}).
Но все же иногда бывает полезен.

Запись макроса:
1. `File -> Macros -> Start Macro Recording`;
2. выполняете желаемую последовательность действий;
3. нажимаете на кнопку остановки записи макроса (PhpStorm 2020.1+), либо `File -> Macros -> End Macro Recording`;
4. вводите желаемое имя макроса.

> Совет: на макрос стоит назначить шорткат.

![Macros usage example](assets/MacrosUsageExample.gif)
