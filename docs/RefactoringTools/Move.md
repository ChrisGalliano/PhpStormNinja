---
parent: Refactoring Tools
nav_order: 2
---

# Refactor: Move

Позволяет перемещать файлы, классы, неймспейсы и методы. После перемещения исправляет все места, которые ссылаются на перемещаемые элементы. Стандартный шорткат - `F6`. Для вызова каретка ввода должна находиться на элементе, который вы хотите переместить.

Вот так, например, происходит перенос метода:<br>
![Move method example](assets/MoveMethodExample.gif)

<br/>

При переносе класса/неймспейса PhpStorm должен автоматически корректно определять директорию, в которую необходимо переместить класс. Если этого не происходит - надо настроить корневые неймспейсы в `Settings -> Directories`.

[https://www.jetbrains.com/help/phpstorm/settings-directories.html](https://www.jetbrains.com/help/phpstorm/settings-directories.html)
