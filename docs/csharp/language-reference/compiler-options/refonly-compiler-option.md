---
title: "-refonly (параметры компилятора C#)"
ms.date: 2017-07-08
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /refonly
dev_langs:
- CSharp
helpviewer_keywords:
- /refonly compiler option [C#]
- -refonly compiler option [C#]
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 81a2252314ef51b5dc01fddc081eb881aa4431a7
ms.openlocfilehash: af99f7565a43dd28b6271611bc8690e7a2e51482
ms.contentlocale: ru-ru
ms.lasthandoff: 08/16/2017

---

# <a name="refonly-c-compiler-options"></a>/refonly (параметры компилятора C#)

Параметр **/refonly** указывает на то, что в качестве основных выходных данных должна быть выведена базовая сборка, а не сборка реализации. Параметр `/refonly` автоматически отключает вывод файлов PDB, так как базовые сборки не могут выполняться.

## <a name="syntax"></a>Синтаксис

```console
/refonly
```

## <a name="remarks"></a>Примечания

Тела методов в сборках, состоящих только из метаданных, заменяются одним телом `throw null`, но такие сборки включают все члены, кроме анонимных типов. Тело `throw null` используется для того, чтобы могло выполняться средство PEVerify для проверки полноты метаданных, что было бы невозможно при отсутствии тела.

Базовые сборки содержат атрибут `ReferenceAssembly` уровня сборки. Этот атрибут может быть задан в исходном коде (в этом случае компилятору не требуется его синтезировать). Из-за этого атрибута среды выполнения не будут загружать базовые сборки для выполнения (однако они могут загружаться в режиме только для отражения). Средства, выполняющие отражение сборок, должны загружать базовые сборки как доступные только для отражения. В противном случае от среды выполнения будет получена ошибка загрузки типа.

Базовые сборки удаляют метаданные (закрытые члены) из сборок, содержащих только метаданные.

- Базовая сборка содержит ссылки только на необходимые компоненты в слое доступа API. Реальная сборка может иметь дополнительные ссылки, связанные с конкретной реализацией. Например, базовая сборка для `class C { private void M() { dynamic d = 1; ... } }` не ссылается на типы, требуемые для `dynamic`.
- Закрытые функции-члены (методы, свойства и события) удаляются в случае, если их удаление не скажется заметно на компиляции. Если нет атрибутов `InternalsVisibleTo`, то же самое выполняется для внутренних функций-членов.
- Однако в базовых сборках сохраняются все типы (включая закрытые и вложенные). Сохраняются все атрибуты (даже внутренние).
- Сохраняются все виртуальные методы. Сохраняются явные реализации интерфейса. Явно реализованные свойства и события сохраняются, так как их методы доступа являются виртуальными (и, следовательно, сохраняются).
- Сохраняются все поля структуры. (Возможно, это будет изменено в версиях после C# 7.1.)

Параметры `/refonly` и [`/refout`](refout-compiler-option.md) являются взаимоисключающими.

## <a name="see-also"></a>См. также
 [Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md)   
 [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
