---
title: Auto Import
nav_order: 5
has_children: false
---
# Auto Import
Settings -> Editor -> General -> Auto Import

Нас интересует блок PHP.

Первая настройка -  `Insert imports on paste`, выбираем `All`.
Теперь при копипасте кода PhpStorm не будет спрашивать, надо ли импортировать классы.
![Insert imports on paste "All" example](assets/InsertImportsOnPasteAll.gif)

<br/>

## Auto-Import Conditions
В этом блоке настраиваются условия срабатывания авто-импорта. Ставим галочки `Enable auto-import in file scope` и `Enable auto-import in namespace scope`.
> Также настоятельно рекомендую выбрать `Treat symbols from the global space -> Class -> prefer FQN`.
> Иначе будут автоимпортиться классы из глобального неймспейса, что совершенно бессмысленно :man_shrugging:.

---

Вот так выглядят мои настройки на текущий момент (PhpStorm 2020.1):
![Screenshot of my settings](assets/AutoImportSettings.png)
