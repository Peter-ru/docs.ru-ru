---
title: "Списки (F#)"
description: "Дополнительные сведения о F # списки, упорядоченная, неизменная серия элементов того же типа."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: a1a6075f-064d-4aee-8222-2b59ff16cc12
ms.openlocfilehash: 5802a5a1c48ad05c1765c4c0fa2e8a81a92dee8d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="lists"></a><span data-ttu-id="07277-104">Списки</span><span class="sxs-lookup"><span data-stu-id="07277-104">Lists</span></span>

> [!NOTE]
<span data-ttu-id="07277-105">Ссылки на справочник по API в этой статье ведут на сайт MSDN.</span><span class="sxs-lookup"><span data-stu-id="07277-105">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="07277-106">Работа над справочником по API docs.microsoft.com не завершена.</span><span class="sxs-lookup"><span data-stu-id="07277-106">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="07277-107">В языке F# список — это упорядоченная, неизменная серия элементов одного типа.</span><span class="sxs-lookup"><span data-stu-id="07277-107">A list in F# is an ordered, immutable series of elements of the same type.</span></span> <span data-ttu-id="07277-108">Для выполнения основных операций со списками используйте функции в [модуль списка](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span><span class="sxs-lookup"><span data-stu-id="07277-108">To perform basic operations on lists, use the functions in the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span>


## <a name="creating-and-initializing-lists"></a><span data-ttu-id="07277-109">Создание и инициализация списков</span><span class="sxs-lookup"><span data-stu-id="07277-109">Creating and Initializing Lists</span></span>
<span data-ttu-id="07277-110">Список можно определить путем прямого перечисления элементов, разделенных точкой с запятой и заключенных в квадратные скобки, как показано в следующей строке кода.</span><span class="sxs-lookup"><span data-stu-id="07277-110">You can define a list by explicitly listing out the elements, separated by semicolons and enclosed in square brackets, as shown in the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1301.fs)]

<span data-ttu-id="07277-111">Вместо точки с запятой для разделения элементов можно также использовать разрыв строки.</span><span class="sxs-lookup"><span data-stu-id="07277-111">You can also put line breaks between elements, in which case the semicolons are optional.</span></span> <span data-ttu-id="07277-112">Такой синтаксис позволяет получить более удобный для чтения код, если список содержит длинные выражения инициализации или к каждому элементу необходимо написать комментарий.</span><span class="sxs-lookup"><span data-stu-id="07277-112">The latter syntax can result in more readable code when the element initialization expressions are longer, or when you want to include a comment for each element.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13011.fs)]

<span data-ttu-id="07277-113">Обычно все элементы в списке должны быть одного типа.</span><span class="sxs-lookup"><span data-stu-id="07277-113">Normally, all list elements must be the same type.</span></span> <span data-ttu-id="07277-114">Исключением является список, в котором элементы основного типа могут иметь элементы производных типов.</span><span class="sxs-lookup"><span data-stu-id="07277-114">An exception is that a list in which the elements are specified to be a base type can have elements that are derived types.</span></span> <span data-ttu-id="07277-115">Следующий вариант считается приемлемым, так как типы `Button` и `CheckBox` являются производными от типа `Control`.</span><span class="sxs-lookup"><span data-stu-id="07277-115">Thus the following is acceptable, because both `Button` and `CheckBox` derive from `Control`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13012.fs)]

<span data-ttu-id="07277-116">Определить элементы списка можно также с помощью диапазона, который будет ограничен целыми числами, разделенными оператором (`..`), как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="07277-116">You can also define list elements by using a range indicated by integers separated by the range operator (`..`), as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1302.fs)]

<span data-ttu-id="07277-117">Пустой список определяется парой квадратных скобок, между которыми ничего не указано.</span><span class="sxs-lookup"><span data-stu-id="07277-117">An empty list is specified by a pair of square brackets with nothing in between them.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1304.fs)]

<span data-ttu-id="07277-118">Также список можно создать с помощью выражения последовательности.</span><span class="sxs-lookup"><span data-stu-id="07277-118">You can also use a sequence expression to create a list.</span></span> <span data-ttu-id="07277-119">В разделе [выражения последовательности](sequences.md#sequence-expressions) для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="07277-119">See [Sequence Expressions](sequences.md#sequence-expressions) for more information.</span></span> <span data-ttu-id="07277-120">Например, в следующем коде создается список квадратов целочисленных значений от 1 до 10.</span><span class="sxs-lookup"><span data-stu-id="07277-120">For example, the following code creates a list of squares of integers from 1 to 10.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1303.fs)]

## <a name="operators-for-working-with-lists"></a><span data-ttu-id="07277-121">Операторы для работы со списками</span><span class="sxs-lookup"><span data-stu-id="07277-121">Operators for Working with Lists</span></span>
<span data-ttu-id="07277-122">Оператор `::` позволяет добавлять элементы в список.</span><span class="sxs-lookup"><span data-stu-id="07277-122">You can attach elements to a list by using the `::` (cons) operator.</span></span> <span data-ttu-id="07277-123">Если список `list1` включает `[2; 3; 4]`, то следующий код создает список `list2` как `[100; 2; 3; 4]`.</span><span class="sxs-lookup"><span data-stu-id="07277-123">If `list1` is `[2; 3; 4]`, the following code creates `list2` as `[100; 2; 3; 4]`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1305.fs)]

<span data-ttu-id="07277-124">Оператор `@` позволяет объединять списки совместимых типов, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="07277-124">You can concatenate lists that have compatible types by using the `@` operator, as in the following code.</span></span> <span data-ttu-id="07277-125">Если список `list1` включает `[2; 3; 4]`, список `list2` — `[100; 2; 3; 4 ]`, то следующий код создает список `list3` как `[2; 3; 4; 100; 2; 3; 4]`.</span><span class="sxs-lookup"><span data-stu-id="07277-125">If `list1` is `[2; 3; 4]` and `list2` is `[100; 2; 3; 4 ]`, this code creates `list3` as `[2; 3; 4; 100; 2; 3; 4]`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1306.fs)]

<span data-ttu-id="07277-126">Доступные функции для выполнения операций со списками в [модуль списка](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span><span class="sxs-lookup"><span data-stu-id="07277-126">Functions for performing operations on lists are available in the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span>

<span data-ttu-id="07277-127">Поскольку списки в языке F# являются неизменными, то операции изменения не изменяют существующие списки, а создают новые.</span><span class="sxs-lookup"><span data-stu-id="07277-127">Because lists in F# are immutable, any modifying operations generate new lists instead of modifying existing lists.</span></span>

<span data-ttu-id="07277-128">Списки в языке F # реализуются как однократно связанные списки, которая означает, что операции, обращающиеся только к началу списка выглядят как O(1), а доступ к элементу — O (*n*).</span><span class="sxs-lookup"><span data-stu-id="07277-128">Lists in F# are implemented as singly linked lists, which means that operations that access only the head of the list are O(1), and element access is O(*n*).</span></span>


## <a name="properties"></a><span data-ttu-id="07277-129">Свойства</span><span class="sxs-lookup"><span data-stu-id="07277-129">Properties</span></span>
<span data-ttu-id="07277-130">Тип списка поддерживает следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="07277-130">The list type supports the following properties:</span></span>

|<span data-ttu-id="07277-131">Свойство</span><span class="sxs-lookup"><span data-stu-id="07277-131">Property</span></span>|<span data-ttu-id="07277-132">Тип</span><span class="sxs-lookup"><span data-stu-id="07277-132">Type</span></span>|<span data-ttu-id="07277-133">Описание</span><span class="sxs-lookup"><span data-stu-id="07277-133">Description</span></span>|
|--------|----|-----------|
|[<span data-ttu-id="07277-134">HEAD</span><span class="sxs-lookup"><span data-stu-id="07277-134">Head</span></span>](https://msdn.microsoft.com/library/5f9414fd-6bdb-470a-8b72-40016db30740)|`'T`|<span data-ttu-id="07277-135">Первый элемент</span><span class="sxs-lookup"><span data-stu-id="07277-135">The first element.</span></span>|
|[<span data-ttu-id="07277-136">Пустой</span><span class="sxs-lookup"><span data-stu-id="07277-136">Empty</span></span>](https://msdn.microsoft.com/library/44406ecb-1918-4d32-b32a-ca1f69840386)|`'T list`|<span data-ttu-id="07277-137">Статическое свойство, которое возвращает пустой список соответствующего типа.</span><span class="sxs-lookup"><span data-stu-id="07277-137">A static property that returns an empty list of the appropriate type.</span></span>|
|[<span data-ttu-id="07277-138">IsEmpty</span><span class="sxs-lookup"><span data-stu-id="07277-138">IsEmpty</span></span>](https://msdn.microsoft.com/library/3ba087b2-2fc2-406d-b10a-cff6a19322da)|`bool`|<span data-ttu-id="07277-139">`true`Если в списке нет элементов.</span><span class="sxs-lookup"><span data-stu-id="07277-139">`true` if the list has no elements.</span></span>|
|[<span data-ttu-id="07277-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="07277-140">Item</span></span>](https://msdn.microsoft.com/library/bdb2553a-0e54-4ff8-baed-ab1aac8f5dae)|`'T`|<span data-ttu-id="07277-141">Элемент с указанным индексом (начинается с нуля).</span><span class="sxs-lookup"><span data-stu-id="07277-141">The element at the specified index (zero-based).</span></span>|
|[<span data-ttu-id="07277-142">Длина</span><span class="sxs-lookup"><span data-stu-id="07277-142">Length</span></span>](https://msdn.microsoft.com/library/25f715c8-9daa-4c4d-a6c7-26772f9dab4d)|`int`|<span data-ttu-id="07277-143">Количество элементов</span><span class="sxs-lookup"><span data-stu-id="07277-143">The number of elements.</span></span>|
|[<span data-ttu-id="07277-144">Резервная копия заключительного</span><span class="sxs-lookup"><span data-stu-id="07277-144">Tail</span></span>](https://msdn.microsoft.com/library/2a6f8eb9-dc32-41aa-8b62-2baffaface91)|`'T list`|<span data-ttu-id="07277-145">Список без первого элемента</span><span class="sxs-lookup"><span data-stu-id="07277-145">The list without the first element.</span></span>|
<span data-ttu-id="07277-146">Ниже приведены некоторые примеры использования данных свойств.</span><span class="sxs-lookup"><span data-stu-id="07277-146">Following are some examples of using these properties.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1307.fs)]
    
## <a name="using-lists"></a><span data-ttu-id="07277-147">Использование списков</span><span class="sxs-lookup"><span data-stu-id="07277-147">Using Lists</span></span>
<span data-ttu-id="07277-148">Программирование с использованием списков позволяет выполнять сложные операции с небольшим количеством кода.</span><span class="sxs-lookup"><span data-stu-id="07277-148">Programming with lists enables you to perform complex operations with a small amount of code.</span></span> <span data-ttu-id="07277-149">В данном разделе описываются операции со списками, важные для функционального программирования.</span><span class="sxs-lookup"><span data-stu-id="07277-149">This section describes common operations on lists that are important to functional programming.</span></span>


### <a name="recursion-with-lists"></a><span data-ttu-id="07277-150">Рекурсия со списками</span><span class="sxs-lookup"><span data-stu-id="07277-150">Recursion with Lists</span></span>
<span data-ttu-id="07277-151">Списки однозначно подходят для техник рекурсивного программирования.</span><span class="sxs-lookup"><span data-stu-id="07277-151">Lists are uniquely suited to recursive programming techniques.</span></span> <span data-ttu-id="07277-152">Рассмотрим операцию, в которой должен участвовать каждый элемент списка.</span><span class="sxs-lookup"><span data-stu-id="07277-152">Consider an operation that must be performed on every element of a list.</span></span> <span data-ttu-id="07277-153">Это можно сделать рекурсивно, т. е. сначала обработать начало списка, затем перейти к хвосту — более короткому списку, состоящему из первоначального списка без первого элемента, а потом снова перейти на следующий уровень рекурсии.</span><span class="sxs-lookup"><span data-stu-id="07277-153">You can do this recursively by operating on the head of the list and then passing the tail of the list, which is a smaller list that consists of the original list without the first element, back again to the next level of recursion.</span></span>

<span data-ttu-id="07277-154">Для написания такой рекурсивной функции используется оператор (`::`) в сопоставлении шаблонов, который позволяет отделить начало списка от хвоста.</span><span class="sxs-lookup"><span data-stu-id="07277-154">To write such a recursive function, you use the cons operator (`::`) in pattern matching, which enables you to separate the head of a list from the tail.</span></span>

<span data-ttu-id="07277-155">Следующий пример кода показывает, как использовать сопоставление шаблонов для реализации рекурсивной функции, выполняющей операции над списком.</span><span class="sxs-lookup"><span data-stu-id="07277-155">The following code example shows how to use pattern matching to implement a recursive function that performs operations on a list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13071.fs)]

<span data-ttu-id="07277-156">Предыдущий код хорошо работает для небольших списков, но при работе со списками большого размера может случиться переполнение стека.</span><span class="sxs-lookup"><span data-stu-id="07277-156">The previous code works well for small lists, but for larger lists, it could overflow the stack.</span></span> <span data-ttu-id="07277-157">Следующий код улучшает предыдущий за счет использования аргумента аккумулирования — это стандартная техника работы с рекурсивными функциями.</span><span class="sxs-lookup"><span data-stu-id="07277-157">The following code improves on this code by using an accumulator argument, a standard technique for working with recursive functions.</span></span> <span data-ttu-id="07277-158">Использование аргумента аккумулирования делает функцию рекурсивной по отношению к хвосту, что экономит место в стеке.</span><span class="sxs-lookup"><span data-stu-id="07277-158">The use of the accumulator argument makes the function tail recursive, which saves stack space.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13072.fs)]

<span data-ttu-id="07277-159">Функция `RemoveAllMultiples` — это рекурсивная функция, которая обрабатывает два списка.</span><span class="sxs-lookup"><span data-stu-id="07277-159">The function `RemoveAllMultiples` is a recursive function that takes two lists.</span></span> <span data-ttu-id="07277-160">Первый список содержит цифры, кратные которым будут удалены, а второй представляет собой список, из которого будут удаляться цифры.</span><span class="sxs-lookup"><span data-stu-id="07277-160">The first list contains the numbers whose multiples will be removed, and the second list is the list from which to remove the numbers.</span></span> <span data-ttu-id="07277-161">Код в следующем примере использует рекурсивную функцию для удаления всех непростых чисел из списка. После его выполнения в списке остаются только простые числа.</span><span class="sxs-lookup"><span data-stu-id="07277-161">The code in the following example uses this recursive function to eliminate all the non-prime numbers from a list, leaving a list of prime numbers as the result.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1308.fs)]

<span data-ttu-id="07277-162">Выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="07277-162">The output is as follows:</span></span>

```
Primes Up To 100:
[2; 3; 5; 7; 11; 13; 17; 19; 23; 29; 31; 37; 41; 43; 47; 53; 59; 61; 67; 71; 73; 79; 83; 89; 97]
```

## <a name="module-functions"></a><span data-ttu-id="07277-163">Функции модуля</span><span class="sxs-lookup"><span data-stu-id="07277-163">Module Functions</span></span>
<span data-ttu-id="07277-164">[Модуль списка](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788) предоставляет функции для доступа к элементам списка.</span><span class="sxs-lookup"><span data-stu-id="07277-164">The [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788) provides functions that access the elements of a list.</span></span> <span data-ttu-id="07277-165">Самым легким и быстрым для доступа является первоначальный элемент.</span><span class="sxs-lookup"><span data-stu-id="07277-165">The head element is the fastest and easiest to access.</span></span> <span data-ttu-id="07277-166">Используйте свойство [Head](https://msdn.microsoft.com/library/5f9414fd-6bdb-470a-8b72-40016db30740) или функция модуля [List.head](https://msdn.microsoft.com/library/22514cc5-0511-498b-a2cc-837b688a6da2).</span><span class="sxs-lookup"><span data-stu-id="07277-166">Use the property [Head](https://msdn.microsoft.com/library/5f9414fd-6bdb-470a-8b72-40016db30740) or the module function [List.head](https://msdn.microsoft.com/library/22514cc5-0511-498b-a2cc-837b688a6da2).</span></span> <span data-ttu-id="07277-167">Доступ к хвосту списка с помощью [заключительного](https://msdn.microsoft.com/library/2a6f8eb9-dc32-41aa-8b62-2baffaface91) свойство или [List.tail](https://msdn.microsoft.com/library/da0a0638-4420-4571-84b6-d09ae601f601) функции.</span><span class="sxs-lookup"><span data-stu-id="07277-167">You can access the tail of a list by using the [Tail](https://msdn.microsoft.com/library/2a6f8eb9-dc32-41aa-8b62-2baffaface91) property or the [List.tail](https://msdn.microsoft.com/library/da0a0638-4420-4571-84b6-d09ae601f601) function.</span></span> <span data-ttu-id="07277-168">Чтобы найти элемент по индексу, используйте [List.nth](https://msdn.microsoft.com/library/1f717d57-89be-4007-a971-9cf5a28d83b1) функции.</span><span class="sxs-lookup"><span data-stu-id="07277-168">To find an element by index, use the [List.nth](https://msdn.microsoft.com/library/1f717d57-89be-4007-a971-9cf5a28d83b1) function.</span></span> <span data-ttu-id="07277-169">`List.nth`проходит по списку.</span><span class="sxs-lookup"><span data-stu-id="07277-169">`List.nth` traverses the list.</span></span> <span data-ttu-id="07277-170">Таким образом, существует O (*n*).</span><span class="sxs-lookup"><span data-stu-id="07277-170">Therefore, it is O(*n*).</span></span> <span data-ttu-id="07277-171">Если в коде часто используется `List.nth`, то вместо списка можно использовать массив.</span><span class="sxs-lookup"><span data-stu-id="07277-171">If your code uses `List.nth` frequently, you might want to consider using an array instead of a list.</span></span> <span data-ttu-id="07277-172">Доступ к элементам массива осуществляется через O(1).</span><span class="sxs-lookup"><span data-stu-id="07277-172">Element access in arrays is O(1).</span></span>


### <a name="boolean-operations-on-lists"></a><span data-ttu-id="07277-173">Логические операции со списками</span><span class="sxs-lookup"><span data-stu-id="07277-173">Boolean Operations on Lists</span></span>
<span data-ttu-id="07277-174">[List.isEmpty](https://msdn.microsoft.com/library/a7941d44-9e92-427c-b806-c378f4558107) функция определяет, имеет ли список какие-либо элементы.</span><span class="sxs-lookup"><span data-stu-id="07277-174">The [List.isEmpty](https://msdn.microsoft.com/library/a7941d44-9e92-427c-b806-c378f4558107) function determines whether a list has any elements.</span></span>

<span data-ttu-id="07277-175">[List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8) функция применяет логический тест к элементам списка и возвращает `true` Если любой элемент проходить этот тест.</span><span class="sxs-lookup"><span data-stu-id="07277-175">The [List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8) function applies a Boolean test to elements of a list and returns `true` if any element satisfies the test.</span></span> <span data-ttu-id="07277-176">[List.exists2](https://msdn.microsoft.com/library/7532b39e-3f4f-4534-a60b-d7721dc6fa7e) аналогична, но работает с последовательными парами элементов в двух списках.</span><span class="sxs-lookup"><span data-stu-id="07277-176">[List.exists2](https://msdn.microsoft.com/library/7532b39e-3f4f-4534-a60b-d7721dc6fa7e) is similar but operates on successive pairs of elements in two lists.</span></span>

<span data-ttu-id="07277-177">В следующем коде показано использование функции `List.exists`.</span><span class="sxs-lookup"><span data-stu-id="07277-177">The following code demonstrates the use of `List.exists`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet1.fs)]

<span data-ttu-id="07277-178">Выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="07277-178">The output is as follows:</span></span>

```
For list [0; 1; 2; 3], contains zero is true
```

<span data-ttu-id="07277-179">В следующем примере показано использование функции `List.exists2`.</span><span class="sxs-lookup"><span data-stu-id="07277-179">The following example demonstrates the use of `List.exists2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet2.fs)]

<span data-ttu-id="07277-180">Выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="07277-180">The output is as follows:</span></span>

```
Lists [1; 2; 3; 4; 5] and [5; 4; 3; 2; 1] have at least one equal element at the same position.
```

<span data-ttu-id="07277-181">Можно использовать [List.forall](https://msdn.microsoft.com/library/e11a5233-d612-40ac-833b-d5cf496900b7) Если вы хотите проверить ли все элементы списка, удовлетворяющих условию.</span><span class="sxs-lookup"><span data-stu-id="07277-181">You can use [List.forall](https://msdn.microsoft.com/library/e11a5233-d612-40ac-833b-d5cf496900b7) if you want to test whether all the elements of a list meet a condition.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet3.fs)]

<span data-ttu-id="07277-182">Выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="07277-182">The output is as follows:</span></span>

```
true
false
```

<span data-ttu-id="07277-183">Аналогичным образом [List.forall2](https://msdn.microsoft.com/library/bb611f02-8277-48f5-9af3-6194ae27d07e) определяет, все ли элементы в соответствующих позициях из двух списков удовлетворяют логическое выражение, которое входит каждая пара элементов.</span><span class="sxs-lookup"><span data-stu-id="07277-183">Similarly, [List.forall2](https://msdn.microsoft.com/library/bb611f02-8277-48f5-9af3-6194ae27d07e) determines whether all elements in the corresponding positions in two lists satisfy a Boolean expression that involves each pair of elements.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet4.fs)]

<span data-ttu-id="07277-184">Выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="07277-184">The output is as follows:</span></span>

```
true
false
```

### <a name="sort-operations-on-lists"></a><span data-ttu-id="07277-185">Операции сортировки списков</span><span class="sxs-lookup"><span data-stu-id="07277-185">Sort Operations on Lists</span></span>
<span data-ttu-id="07277-186">[List.sort](https://msdn.microsoft.com/library/17f1030e-aa7e-41dd-94ea-72cb6c04fd3d), [List.sortBy](https://msdn.microsoft.com/library/955bfc5f-ad9c-4f2d-a7ab-91e43eb21359), и [List.sortWith](https://msdn.microsoft.com/library/1d806a54-9166-4198-906d-15101f7916c7) функции сортировки списков.</span><span class="sxs-lookup"><span data-stu-id="07277-186">The [List.sort](https://msdn.microsoft.com/library/17f1030e-aa7e-41dd-94ea-72cb6c04fd3d), [List.sortBy](https://msdn.microsoft.com/library/955bfc5f-ad9c-4f2d-a7ab-91e43eb21359), and [List.sortWith](https://msdn.microsoft.com/library/1d806a54-9166-4198-906d-15101f7916c7) functions sort lists.</span></span> <span data-ttu-id="07277-187">Функция сортировки определяет, какую из этих трех функций использовать.</span><span class="sxs-lookup"><span data-stu-id="07277-187">The sorting function determines which of these three functions to use.</span></span> <span data-ttu-id="07277-188">`List.sort`использует общего сравнения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="07277-188">`List.sort` uses default generic comparison.</span></span> <span data-ttu-id="07277-189">Общее сравнение выполняется с помощью глобальных операторов на основе функции общего сравнения значений.</span><span class="sxs-lookup"><span data-stu-id="07277-189">Generic comparison uses global operators based on the generic compare function to compare values.</span></span> <span data-ttu-id="07277-190">Оно эффективно работает с различными типами элементов, такими как числовые типы, кортежи, записи, размеченные объединения, списки, массивы и любой другой тип, включающий `System.IComparable`.</span><span class="sxs-lookup"><span data-stu-id="07277-190">It works efficiently with a wide variety of element types, such as simple numeric types, tuples, records, discriminated unions, lists, arrays, and any type that implements `System.IComparable`.</span></span> <span data-ttu-id="07277-191">Для типов, включающих `System.IComparable`, общее сравнение выполняется с помощью функции `System.IComparable.CompareTo()`.</span><span class="sxs-lookup"><span data-stu-id="07277-191">For types that implement `System.IComparable`, generic comparison uses the `System.IComparable.CompareTo()` function.</span></span> <span data-ttu-id="07277-192">Общее сравнение также работает со строками, но использует культурно-независимый порядок сортировки.</span><span class="sxs-lookup"><span data-stu-id="07277-192">Generic comparison also works with strings, but uses a culture-independent sorting order.</span></span> <span data-ttu-id="07277-193">Общее сравнение не следует применять к неподдерживаемым типам, например типам функций.</span><span class="sxs-lookup"><span data-stu-id="07277-193">Generic comparison should not be used on unsupported types, such as function types.</span></span> <span data-ttu-id="07277-194">К тому же выполнение общего сравнения по умолчанию лучше всего подходит для слабо структурированных типов. Для сильно структурированных типов, которые необходимо часто сравнивать и сортировать, можно использовать функцию `System.IComparable` и метод `System.IComparable.CompareTo()`.</span><span class="sxs-lookup"><span data-stu-id="07277-194">Also, the performance of the default generic comparison is best for small structured types; for larger structured types that need to be compared and sorted frequently, consider implementing `System.IComparable` and providing an efficient implementation of the `System.IComparable.CompareTo()` method.</span></span>

<span data-ttu-id="07277-195">`List.sortBy`принимает функция, которая возвращает значение, которое используется в качестве критерия сортировки и `List.sortWith` принимает функцию сравнения в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="07277-195">`List.sortBy` takes a function that returns a value that is used as the sort criterion, and `List.sortWith` takes a comparison function as an argument.</span></span> <span data-ttu-id="07277-196">Две последние функции полезны при работе с типами, которые не поддерживают сравнение, а также если сравнение требует более сложной семантики, например в случае со строками, учитывающими язык и регион.</span><span class="sxs-lookup"><span data-stu-id="07277-196">These latter two functions are useful when you are working with types that do not support comparison, or when the comparison requires more complex comparison semantics, as in the case of culture-aware strings.</span></span>

<span data-ttu-id="07277-197">В следующем примере показано использование функции `List.sort`.</span><span class="sxs-lookup"><span data-stu-id="07277-197">The following example demonstrates the use of `List.sort`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet5.fs)]

<span data-ttu-id="07277-198">Выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="07277-198">The output is as follows:</span></span>

```
[-2; 1; 4; 5; 8]
```

<span data-ttu-id="07277-199">В следующем примере показано использование функции `List.sortBy`.</span><span class="sxs-lookup"><span data-stu-id="07277-199">The following example demonstrates the use of `List.sortBy`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet6.fs)]

<span data-ttu-id="07277-200">Выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="07277-200">The output is as follows:</span></span>

```
[1; -2; 4; 5; 8]
```

<span data-ttu-id="07277-201">В следующем примере показано использование `List.sortWith`.</span><span class="sxs-lookup"><span data-stu-id="07277-201">The next example demonstrates the use of `List.sortWith`.</span></span> <span data-ttu-id="07277-202">В этом примере обычная функция сравнения `compareWidgets` используется сначала для сравнения одного поля пользовательского типа, а затем другого, если значения первого поля равны.</span><span class="sxs-lookup"><span data-stu-id="07277-202">In this example, the custom comparison function `compareWidgets` is used to first compare one field of a custom type, and then another when the values of the first field are equal.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet7.fs)]

<span data-ttu-id="07277-203">Выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="07277-203">The output is as follows:</span></span>

```
[{ID = 92;
Rev = 1;}; {ID = 92;
Rev = 1;}; {ID = 100;
Rev = 2;}; {ID = 100;
Rev = 5;}; {ID = 110;
Rev = 1;}]
```

### <a name="search-operations-on-lists"></a><span data-ttu-id="07277-204">Операции поиска в списках</span><span class="sxs-lookup"><span data-stu-id="07277-204">Search Operations on Lists</span></span>
<span data-ttu-id="07277-205">Списки поддерживают различные операции поиска.</span><span class="sxs-lookup"><span data-stu-id="07277-205">Numerous search operations are supported for lists.</span></span> <span data-ttu-id="07277-206">Самая простая, [List.find](https://msdn.microsoft.com/library/0594593e-9c75-44c1-8f5a-a37b2e561c06), позволяет найти первый элемент, который удовлетворяет заданному условию.</span><span class="sxs-lookup"><span data-stu-id="07277-206">The simplest, [List.find](https://msdn.microsoft.com/library/0594593e-9c75-44c1-8f5a-a37b2e561c06), enables you to find the first element that matches a given condition.</span></span>

<span data-ttu-id="07277-207">В следующем примере кода показано, как использовать `List.find` для поиска первого числа в списке, которое делится на 5.</span><span class="sxs-lookup"><span data-stu-id="07277-207">The following code example demonstrates the use of `List.find` to find the first number that is divisible by 5 in a list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet8.fs)]

<span data-ttu-id="07277-208">Результат — 5.</span><span class="sxs-lookup"><span data-stu-id="07277-208">The result is 5.</span></span>

<span data-ttu-id="07277-209">Если вначале требуется трансформировать элементы, вызовите [List.pick](https://msdn.microsoft.com/library/0430b515-7fe4-49a1-a616-d2286d8b08b2), который использует функцию, возвращающую параметр, и ищет первый вариант значение — `Some(x)`.</span><span class="sxs-lookup"><span data-stu-id="07277-209">If the elements must be transformed first, call [List.pick](https://msdn.microsoft.com/library/0430b515-7fe4-49a1-a616-d2286d8b08b2), which takes a function that returns an option, and looks for the first option value that is `Some(x)`.</span></span> <span data-ttu-id="07277-210">Вместо возвращения элемента функция `List.pick` возвращает результат `x`.</span><span class="sxs-lookup"><span data-stu-id="07277-210">Instead of returning the element, `List.pick` returns the result `x`.</span></span> <span data-ttu-id="07277-211">Если совпадения не найдены, функция `List.pick` возвращает `System.Collections.Generic.KeyNotFoundException`.</span><span class="sxs-lookup"><span data-stu-id="07277-211">If no matching element is found, `List.pick` throws `System.Collections.Generic.KeyNotFoundException`.</span></span> <span data-ttu-id="07277-212">В следующем коде показано использование `List.pick`.</span><span class="sxs-lookup"><span data-stu-id="07277-212">The following code shows the use of `List.pick`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet9.fs)]

<span data-ttu-id="07277-213">Выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="07277-213">The output is as follows:</span></span>

```
"b"
```

<span data-ttu-id="07277-214">Другая группа операций поиска, [List.tryFind](https://msdn.microsoft.com/library/37f4532e-9fd0-4802-8bbd-e1aa2380287d) и связанные функции возвращают значение параметра.</span><span class="sxs-lookup"><span data-stu-id="07277-214">Another group of search operations, [List.tryFind](https://msdn.microsoft.com/library/37f4532e-9fd0-4802-8bbd-e1aa2380287d) and related functions, return an option value.</span></span> <span data-ttu-id="07277-215">Функция `List.tryFind` возвращает первый элемент списка, который удовлетворяет условию, если такой элемент есть, и значение параметра `None`, если нет.</span><span class="sxs-lookup"><span data-stu-id="07277-215">The `List.tryFind` function returns the first element of a list that satisfies a condition if such an element exists, but the option value `None` if not.</span></span> <span data-ttu-id="07277-216">Значение варианта [List.tryFindIndex](https://msdn.microsoft.com/library/5e31968c-c3d3-43d2-859a-0526825895ec) возвращает индекс элемента, если он найден, а не сам элемент.</span><span class="sxs-lookup"><span data-stu-id="07277-216">The variation [List.tryFindIndex](https://msdn.microsoft.com/library/5e31968c-c3d3-43d2-859a-0526825895ec) returns the index of the element, if one is found, rather than the element itself.</span></span> <span data-ttu-id="07277-217">Эти функции представлены в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="07277-217">These functions are illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet10.fs)]

<span data-ttu-id="07277-218">Выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="07277-218">The output is as follows:</span></span>

```
The first even value is 22.
The first even value is at position 8.
```

### <a name="arithmetic-operations-on-lists"></a><span data-ttu-id="07277-219">Арифметические операции со списками</span><span class="sxs-lookup"><span data-stu-id="07277-219">Arithmetic Operations on Lists</span></span>
<span data-ttu-id="07277-220">Стандартные арифметические операции, такие как сумма и среднее, встроены в [модуль списка](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span><span class="sxs-lookup"><span data-stu-id="07277-220">Common arithmetic operations such as sum and average are built into the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span> <span data-ttu-id="07277-221">Для работы с [List.sum](https://msdn.microsoft.com/library/54d47fe3-5ecf-4883-beb5-e915342a17f9), должен поддерживать тип элемента списка `+` оператор и иметь нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="07277-221">To work with [List.sum](https://msdn.microsoft.com/library/54d47fe3-5ecf-4883-beb5-e915342a17f9), the list element type must support the `+` operator and have a zero value.</span></span> <span data-ttu-id="07277-222">Все встроенные арифметические типы удовлетворяют этим условиям.</span><span class="sxs-lookup"><span data-stu-id="07277-222">All built-in arithmetic types satisfy these conditions.</span></span> <span data-ttu-id="07277-223">Для работы с [List.average](https://msdn.microsoft.com/library/2b9a627b-106d-4548-8c4c-ab5058b8f8e1), тип элемента должен поддерживать деление без остатка, что исключает целочисленные типы, но разрешает типами с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="07277-223">To work with [List.average](https://msdn.microsoft.com/library/2b9a627b-106d-4548-8c4c-ab5058b8f8e1), the element type must support division without a remainder, which excludes integral types but allows for floating point types.</span></span> <span data-ttu-id="07277-224">[List.sumBy](https://msdn.microsoft.com/library/b7623389-0fe1-4762-9c67-51079903ab7d) и [List.averageBy](https://msdn.microsoft.com/library/936cc9ec-62af-464d-8726-7999c2f48403) функции принимают функцию в качестве параметра, и эта функция используется для расчета суммы или среднего значения.</span><span class="sxs-lookup"><span data-stu-id="07277-224">The [List.sumBy](https://msdn.microsoft.com/library/b7623389-0fe1-4762-9c67-51079903ab7d) and [List.averageBy](https://msdn.microsoft.com/library/936cc9ec-62af-464d-8726-7999c2f48403) functions take a function as a parameter, and this function's results are used to calculate the values for the sum or average.</span></span>

<span data-ttu-id="07277-225">В следующем коде показано использование `List.sum`, `List.sumBy` и `List.average`.</span><span class="sxs-lookup"><span data-stu-id="07277-225">The following code demonstrates the use of `List.sum`, `List.sumBy`, and `List.average`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet11.fs)]

<span data-ttu-id="07277-226">В результате получается `1.000000`.</span><span class="sxs-lookup"><span data-stu-id="07277-226">The output is `1.000000`.</span></span>

<span data-ttu-id="07277-227">В следующем коде показано использование `List.averageBy`.</span><span class="sxs-lookup"><span data-stu-id="07277-227">The following code shows the use of `List.averageBy`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet12.fs)]

<span data-ttu-id="07277-228">В результате получается `5.5`.</span><span class="sxs-lookup"><span data-stu-id="07277-228">The output is `5.5`.</span></span>


### <a name="lists-and-tuples"></a><span data-ttu-id="07277-229">Списки и кортежи</span><span class="sxs-lookup"><span data-stu-id="07277-229">Lists and Tuples</span></span>
<span data-ttu-id="07277-230">Для работы со списками, содержащими кортежи, можно использовать функции упаковки и распаковки.</span><span class="sxs-lookup"><span data-stu-id="07277-230">Lists that contain tuples can be manipulated by zip and unzip functions.</span></span> <span data-ttu-id="07277-231">Они объединяют два списка с одним значением в один список кортежей или разбивают один список кортежей на два списка с одним значением.</span><span class="sxs-lookup"><span data-stu-id="07277-231">These functions combine two lists of single values into one list of tuples or separate one list of tuples into two lists of single values.</span></span> <span data-ttu-id="07277-232">Наиболее простым [List.zip](https://msdn.microsoft.com/library/3028d790-8f48-4c94-bf08-b058bec3689c) функция принимает два списка отдельных элементов и создает один список пар кортежей.</span><span class="sxs-lookup"><span data-stu-id="07277-232">The simplest [List.zip](https://msdn.microsoft.com/library/3028d790-8f48-4c94-bf08-b058bec3689c) function takes two lists of single elements and produces a single list of tuple pairs.</span></span> <span data-ttu-id="07277-233">Другая версия [List.zip3](https://msdn.microsoft.com/library/003cc28e-0de3-4d99-89ed-cb19028e3c5b), берет три списка с одним элементом и создает один список кортежей с тремя элементами.</span><span class="sxs-lookup"><span data-stu-id="07277-233">Another version, [List.zip3](https://msdn.microsoft.com/library/003cc28e-0de3-4d99-89ed-cb19028e3c5b), takes three lists of single elements and produces a single list of tuples that have three elements.</span></span> <span data-ttu-id="07277-234">В следующем коде показано использование функции `List.zip`.</span><span class="sxs-lookup"><span data-stu-id="07277-234">The following code example demonstrates the use of `List.zip`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet13.fs)]

<span data-ttu-id="07277-235">Выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="07277-235">The output is as follows:</span></span>

```
[(1, -1); (2, -2); (3; -3)]
```

<span data-ttu-id="07277-236">В следующем коде показано использование функции `List.zip3`.</span><span class="sxs-lookup"><span data-stu-id="07277-236">The following code example demonstrates the use of `List.zip3`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet14.fs)]

<span data-ttu-id="07277-237">Выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="07277-237">The output is as follows:</span></span>

```
[(1, -1, 0); (2, -2, 0); (3, -3, 0)]
```

<span data-ttu-id="07277-238">Соответствующие версии распаковки, [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21) и [List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4), принимают списки кортежей и возвращают списки в кортеж, где первый список содержит все элементы, которые были первыми в каждом кортеже и второй содержит второй элемент каждого кортежа и т. д.</span><span class="sxs-lookup"><span data-stu-id="07277-238">The corresponding unzip versions, [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21) and [List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4), take lists of tuples and return lists in a tuple, where the first list contains all the elements that were first in each tuple, and the second list contains the second element of each tuple, and so on.</span></span>

<span data-ttu-id="07277-239">В следующем примере кода показано использование [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).</span><span class="sxs-lookup"><span data-stu-id="07277-239">The following code example demonstrates the use of [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet15.fs)]

<span data-ttu-id="07277-240">Выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="07277-240">The output is as follows:</span></span>

```
([1; 3], [2; 4])
[1; 3] [2; 4]
```

<span data-ttu-id="07277-241">В следующем примере кода показано использование [List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4).</span><span class="sxs-lookup"><span data-stu-id="07277-241">The following code example demonstrates the use of [List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet16.fs)]

<span data-ttu-id="07277-242">Выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="07277-242">The output is as follows:</span></span>

```
([1; 4], [2; 5], [3; 6])
```

### <a name="operating-on-list-elements"></a><span data-ttu-id="07277-243">Операции с элементами списка</span><span class="sxs-lookup"><span data-stu-id="07277-243">Operating on List Elements</span></span>
<span data-ttu-id="07277-244">F# поддерживает различные операции с элементами списка.</span><span class="sxs-lookup"><span data-stu-id="07277-244">F# supports a variety of operations on list elements.</span></span> <span data-ttu-id="07277-245">Самым простым является [List.iter](https://msdn.microsoft.com/library/f778d075-81a9-4994-af60-cddcc53a201f), что позволяет вызвать функцию для каждого элемента списка.</span><span class="sxs-lookup"><span data-stu-id="07277-245">The simplest is [List.iter](https://msdn.microsoft.com/library/f778d075-81a9-4994-af60-cddcc53a201f), which enables you to call a function on every element of a list.</span></span> <span data-ttu-id="07277-246">Варианты включать в себя [List.iter2](https://msdn.microsoft.com/library/ea3b7761-916c-4016-9bd8-651124c98b40), позволяет выполнять операцию над элементами двух списков, [List.iteri](https://msdn.microsoft.com/library/6dd21ae6-5c00-41cd-8306-821e513d8f60), а `List.iter` за исключением того, что индекс каждого элемента передается как аргумент в функцию, которая вызывается для каждого элемента и [List.iteri2](https://msdn.microsoft.com/library/9658d740-9be5-4bf7-b663-c8ab2b3e196c), который представляет собой комбинацию функциональных возможностей `List.iter2` и `List.iteri`.</span><span class="sxs-lookup"><span data-stu-id="07277-246">Variations include [List.iter2](https://msdn.microsoft.com/library/ea3b7761-916c-4016-9bd8-651124c98b40), which enables you to perform an operation on elements of two lists, [List.iteri](https://msdn.microsoft.com/library/6dd21ae6-5c00-41cd-8306-821e513d8f60), which is like `List.iter` except that the index of each element is passed as an argument to the function that is called for each element, and [List.iteri2](https://msdn.microsoft.com/library/9658d740-9be5-4bf7-b663-c8ab2b3e196c), which is a combination of the functionality of `List.iter2` and `List.iteri`.</span></span> <span data-ttu-id="07277-247">Эти функции показаны в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="07277-247">The following code example illustrates these functions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet17.fs)]

<span data-ttu-id="07277-248">Выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="07277-248">The output is as follows:</span></span>

```
List.iter: element is 1
List.iter: element is 2
List.iter: element is 3
List.iteri: element 0 is 1
List.iteri: element 1 is 2
List.iteri: element 2 is 3
List.iter2: elements are 1 4
List.iter2: elements are 2 5
List.iter2: elements are 3 6
List.iteri2: element 0 of list1 is 1; element 0 of list2 is 4
List.iteri2: element 1 of list1 is 2; element 1 of list2 is 5
List.iteri2: element 2 of list1 is 3; element 2 of list2 is 6
```

<span data-ttu-id="07277-249">Другая часто используемая функция, преобразующая элементы списка — [List.map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6), что позволяет применить функцию к каждому элементу списка и поместить результаты в новый список.</span><span class="sxs-lookup"><span data-stu-id="07277-249">Another frequently used function that transforms list elements is [List.map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6), which enables you to apply a function to each element of a list and put all the results into a new list.</span></span> <span data-ttu-id="07277-250">[List.map2](https://msdn.microsoft.com/library/5f48cce7-6eaf-4e54-8996-2b04d3c31e57) и [List.map3](https://msdn.microsoft.com/library/dd9fb190-6980-4537-be96-5645a64908f8) это варианты, принимающие несколько списков.</span><span class="sxs-lookup"><span data-stu-id="07277-250">[List.map2](https://msdn.microsoft.com/library/5f48cce7-6eaf-4e54-8996-2b04d3c31e57) and [List.map3](https://msdn.microsoft.com/library/dd9fb190-6980-4537-be96-5645a64908f8) are variations that take multiple lists.</span></span> <span data-ttu-id="07277-251">Можно также использовать [List.mapi](https://msdn.microsoft.com/library/284b9234-3d26-409b-b328-ac79638d9e14) и [List.mapi2](https://msdn.microsoft.com/library/680643af-233c-40a3-82f2-43d5af27ec49), если наряду с элементом функции необходимо передать также индекс каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="07277-251">You can also use [List.mapi](https://msdn.microsoft.com/library/284b9234-3d26-409b-b328-ac79638d9e14) and [List.mapi2](https://msdn.microsoft.com/library/680643af-233c-40a3-82f2-43d5af27ec49), if, in addition to the element, the function needs to be passed the index of each element.</span></span> <span data-ttu-id="07277-252">Единственное различие между `List.mapi2` и `List.mapi` состоит в том, что функция `List.mapi2` работает с двумя списками.</span><span class="sxs-lookup"><span data-stu-id="07277-252">The only difference between `List.mapi2` and `List.mapi` is that `List.mapi2` works with two lists.</span></span> <span data-ttu-id="07277-253">В следующем примере демонстрируется [List.map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6).</span><span class="sxs-lookup"><span data-stu-id="07277-253">The following example illustrates [List.map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet18.fs)]

<span data-ttu-id="07277-254">Выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="07277-254">The output is as follows:</span></span>

```
[2; 3; 4]
```

<span data-ttu-id="07277-255">В следующем коде показано использование функции `List.map2`.</span><span class="sxs-lookup"><span data-stu-id="07277-255">The following example shows the use of `List.map2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet19.fs)]

<span data-ttu-id="07277-256">Выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="07277-256">The output is as follows:</span></span>

```
[5; 7; 9]
```

<span data-ttu-id="07277-257">В следующем коде показано использование функции `List.map3`.</span><span class="sxs-lookup"><span data-stu-id="07277-257">The following example shows the use of `List.map3`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet20.fs)]

<span data-ttu-id="07277-258">Выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="07277-258">The output is as follows:</span></span>

```
[7; 10; 13]
```

<span data-ttu-id="07277-259">В следующем коде показано использование функции `List.mapi`.</span><span class="sxs-lookup"><span data-stu-id="07277-259">The following example shows the use of `List.mapi`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet21.fs)]

<span data-ttu-id="07277-260">Выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="07277-260">The output is as follows:</span></span>

```
[1; 3; 5]
```

<span data-ttu-id="07277-261">В следующем коде показано использование функции `List.mapi2`.</span><span class="sxs-lookup"><span data-stu-id="07277-261">The following example shows the use of `List.mapi2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet22.fs)]

<span data-ttu-id="07277-262">Выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="07277-262">The output is as follows:</span></span>

```
[0; 7; 18]
```

<span data-ttu-id="07277-263">[List.Collect](https://msdn.microsoft.com/library/cd08bbc7-a3b9-40ab-8c20-4e85ec84664f) подобно `List.map`, за исключением того, что каждый элемент создается список, и все эти списки сцепляются в конечный список.</span><span class="sxs-lookup"><span data-stu-id="07277-263">[List.collect](https://msdn.microsoft.com/library/cd08bbc7-a3b9-40ab-8c20-4e85ec84664f) is like `List.map`, except that each element produces a list and all these lists are concatenated into a final list.</span></span> <span data-ttu-id="07277-264">В следующем коде каждый элемент списка генерирует три числа.</span><span class="sxs-lookup"><span data-stu-id="07277-264">In the following code, each element of the list generates three numbers.</span></span> <span data-ttu-id="07277-265">Все они собираются в один список.</span><span class="sxs-lookup"><span data-stu-id="07277-265">These are all collected into one list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet23.fs)]

<span data-ttu-id="07277-266">Выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="07277-266">The output is as follows:</span></span>

```
[1; 2; 3; 2; 4; 6; 3; 6; 9]
```

<span data-ttu-id="07277-267">Можно также использовать [List.filter](https://msdn.microsoft.com/library/11a8c926-547b-44dd-bbae-98d44f3dd248), который принимает логическое условие и создает новый список, содержащий только элементы, которые удовлетворяют заданному условию.</span><span class="sxs-lookup"><span data-stu-id="07277-267">You can also use [List.filter](https://msdn.microsoft.com/library/11a8c926-547b-44dd-bbae-98d44f3dd248), which takes a Boolean condition and produces a new list that consists only of elements that satisfy the given condition.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet24.fs)]

<span data-ttu-id="07277-268">Результатом является список `[2; 4; 6]`.</span><span class="sxs-lookup"><span data-stu-id="07277-268">The resulting list is `[2; 4; 6]`.</span></span>

<span data-ttu-id="07277-269">Сочетание сопоставление и фильтрацию [List.choose](https://msdn.microsoft.com/library/2e21d3fb-ce35-4824-8a57-c4404616093d) позволяет трансформировать и выбирать элементы одновременно.</span><span class="sxs-lookup"><span data-stu-id="07277-269">A combination of map and filter, [List.choose](https://msdn.microsoft.com/library/2e21d3fb-ce35-4824-8a57-c4404616093d) enables you to transform and select elements at the same time.</span></span> <span data-ttu-id="07277-270">`List.choose`Применяет функцию, возвращающую параметр для каждого элемента списка и возвращает новый список результатов для элементов, для которых функция возвращает значение параметра `Some`.</span><span class="sxs-lookup"><span data-stu-id="07277-270">`List.choose` applies a function that returns an option to each element of a list, and returns a new list of the results for elements when the function returns the option value `Some`.</span></span>

<span data-ttu-id="07277-271">В следующем коде показано использование функции `List.choose` для выбора из списка слов с заглавными буквами.</span><span class="sxs-lookup"><span data-stu-id="07277-271">The following code demonstrates the use of `List.choose` to select capitalized words out of a list of words.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet25.fs)]

<span data-ttu-id="07277-272">Выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="07277-272">The output is as follows:</span></span>

```
["Rome's"; "Bob's"]
```

### <a name="operating-on-multiple-lists"></a><span data-ttu-id="07277-273">Операции с несколькими списками</span><span class="sxs-lookup"><span data-stu-id="07277-273">Operating on Multiple Lists</span></span>
<span data-ttu-id="07277-274">Списки могут быть объединены.</span><span class="sxs-lookup"><span data-stu-id="07277-274">Lists can be joined together.</span></span> <span data-ttu-id="07277-275">Чтобы объединить два списка в один, используйте [List.append](https://msdn.microsoft.com/library/2954da80-3f4a-4a4b-9371-794645c03426).</span><span class="sxs-lookup"><span data-stu-id="07277-275">To join two lists into one, use [List.append](https://msdn.microsoft.com/library/2954da80-3f4a-4a4b-9371-794645c03426).</span></span> <span data-ttu-id="07277-276">Чтобы объединить больше двух списков, используется [List.concat](https://msdn.microsoft.com/library/c5afd433-8764-4ea8-a6a8-937fb4d77c4c).</span><span class="sxs-lookup"><span data-stu-id="07277-276">To join more than two lists, use [List.concat](https://msdn.microsoft.com/library/c5afd433-8764-4ea8-a6a8-937fb4d77c4c).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet26.fs)]
    
### <a name="fold-and-scan-operations"></a><span data-ttu-id="07277-277">Операции свертывания и сканирования</span><span class="sxs-lookup"><span data-stu-id="07277-277">Fold and Scan Operations</span></span>
<span data-ttu-id="07277-278">Некоторые операции со списками включают взаимозависимости между всеми элементами списка.</span><span class="sxs-lookup"><span data-stu-id="07277-278">Some list operations involve interdependencies between all of the list elements.</span></span> <span data-ttu-id="07277-279">Операции свертывания и сканирования похожи `List.iter` и `List.map` , вызова функции для каждого элемента, но включают дополнительный параметр, называемый *аккумулятор* , содержит конфиденциальную информацию вычисление.</span><span class="sxs-lookup"><span data-stu-id="07277-279">The fold and scan operations are like `List.iter` and `List.map` in that you invoke a function on each element, but these operations provide an additional parameter called the *accumulator* that carries information through the computation.</span></span>

<span data-ttu-id="07277-280">`List.fold` можно использовать для выполнения расчетов со списком.</span><span class="sxs-lookup"><span data-stu-id="07277-280">Use `List.fold` to perform a calculation on a list.</span></span>

<span data-ttu-id="07277-281">В следующем примере кода показано использование [List.fold](https://msdn.microsoft.com/library/c272779e-bae7-4983-8d7f-16b345bb33a0) для выполнения различных операций.</span><span class="sxs-lookup"><span data-stu-id="07277-281">The following code example demonstrates the use of [List.fold](https://msdn.microsoft.com/library/c272779e-bae7-4983-8d7f-16b345bb33a0) to perform various operations.</span></span>

<span data-ttu-id="07277-282">Лист обходится. Аккумулятор `acc` — это значение, которое передается дальше, пока продолжается расчет.</span><span class="sxs-lookup"><span data-stu-id="07277-282">The list is traversed; the accumulator `acc` is a value that is passed along as the calculation proceeds.</span></span> <span data-ttu-id="07277-283">Первый аргумент забирает аккумулятор и элемент списка и возвращает промежуточный результат расчета для этого элемента списка.</span><span class="sxs-lookup"><span data-stu-id="07277-283">The first argument takes the accumulator and the list element, and returns the interim result of the calculation for that list element.</span></span> <span data-ttu-id="07277-284">Второй аргумент является исходным значением аккумулятора.</span><span class="sxs-lookup"><span data-stu-id="07277-284">The second argument is the initial value of the accumulator.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet27.fs)]

<span data-ttu-id="07277-285">Версии этих функций с цифрой в имени функции работают с несколькими списками.</span><span class="sxs-lookup"><span data-stu-id="07277-285">The versions of these functions that have a digit in the function name operate on more than one list.</span></span> <span data-ttu-id="07277-286">Например [List.fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) выполняет вычисления с двумя списками.</span><span class="sxs-lookup"><span data-stu-id="07277-286">For example, [List.fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) performs computations on two lists.</span></span>

<span data-ttu-id="07277-287">В следующем примере показано использование функции `List.fold2`.</span><span class="sxs-lookup"><span data-stu-id="07277-287">The following example demonstrates the use of `List.fold2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet28.fs)]

<span data-ttu-id="07277-288">`List.fold`и [List.scan](https://msdn.microsoft.com/library/21f636db-885c-4a72-970e-e3841f33a1b8) отличаются тем, что `List.fold` возвращает окончательное значение дополнительного параметра, но `List.scan` возвращает список промежуточных значений дополнительного параметра (и его окончательное значение).</span><span class="sxs-lookup"><span data-stu-id="07277-288">`List.fold` and [List.scan](https://msdn.microsoft.com/library/21f636db-885c-4a72-970e-e3841f33a1b8) differ in that `List.fold` returns the final value of the extra parameter, but `List.scan` returns the list of the intermediate values (along with the final value) of the extra parameter.</span></span>

<span data-ttu-id="07277-289">Каждая из этих функций включает обратную вариацию, например [List.foldBack](https://msdn.microsoft.com/library/b9a58e66-efe1-445f-a90c-ac9ffb9d40c7), и отличается в порядке обхода списка и в порядке аргументов.</span><span class="sxs-lookup"><span data-stu-id="07277-289">Each of these functions includes a reverse variation, for example, [List.foldBack](https://msdn.microsoft.com/library/b9a58e66-efe1-445f-a90c-ac9ffb9d40c7), which differs in the order in which the list is traversed and the order of the arguments.</span></span> <span data-ttu-id="07277-290">Кроме того `List.fold` и `List.foldBack` имеют вариации, [List.fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) и [List.foldBack2](https://msdn.microsoft.com/library/56371d3e-5271-4183-9e8c-15a02eda9aa2), которые берут два списка одинаковой длины.</span><span class="sxs-lookup"><span data-stu-id="07277-290">Also, `List.fold` and `List.foldBack` have variations, [List.fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) and [List.foldBack2](https://msdn.microsoft.com/library/56371d3e-5271-4183-9e8c-15a02eda9aa2), that take two lists of equal length.</span></span> <span data-ttu-id="07277-291">Функция, которая выполняется по каждому элементу, может использовать соответствующие элементы обоих списков для выполнения некоторых действий.</span><span class="sxs-lookup"><span data-stu-id="07277-291">The function that executes on each element can use corresponding elements of both lists to perform some action.</span></span> <span data-ttu-id="07277-292">Типы элементов этих списков могут отличаться, как в следующем примере, где один список содержит суммы транзакций на банковском счете, а другой — типы транзакций (внесение или снятие).</span><span class="sxs-lookup"><span data-stu-id="07277-292">The element types of the two lists can be different, as in the following example, in which one list contains transaction amounts for a bank account, and the other list contains the type of transaction: deposit or withdrawal.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet29.fs)]

<span data-ttu-id="07277-293">При расчете суммы функции `List.fold` и `List.foldBack` действуют одинаково, так как результат не зависит от порядка обхода.</span><span class="sxs-lookup"><span data-stu-id="07277-293">For a calculation like summation, `List.fold` and `List.foldBack` have the same effect because the result does not depend on the order of traversal.</span></span> <span data-ttu-id="07277-294">В следующем примере кода функция `List.foldBack` используется для добавления элемента в список.</span><span class="sxs-lookup"><span data-stu-id="07277-294">In the following example, `List.foldBack` is used to add the elements in a list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet30.fs)]

<span data-ttu-id="07277-295">В следующем примере снова используется банковский счет.</span><span class="sxs-lookup"><span data-stu-id="07277-295">The following example returns to the bank account example.</span></span> <span data-ttu-id="07277-296">В этот раз добавляется новый тип транзакций: расчет процентов.</span><span class="sxs-lookup"><span data-stu-id="07277-296">This time a new transaction type is added: an interest calculation.</span></span> <span data-ttu-id="07277-297">Конечный баланс теперь зависит от порядка транзакций.</span><span class="sxs-lookup"><span data-stu-id="07277-297">The ending balance now depends on the order of transactions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet34.fs)]

<span data-ttu-id="07277-298">Функция [List.reduce](https://msdn.microsoft.com/library/048e1f95-691b-49cb-bb99-fb85f68f3d8b) похожа `List.fold` и `List.scan`, за исключением того, что вместо передачи отдельного аккумулятора `List.reduce` принимает функцию, которая принимает два аргумента типа элемента вместо только один и один из этих аргументов выполняет роль аккумулятора, т. е. хранит промежуточный результат вычисления.</span><span class="sxs-lookup"><span data-stu-id="07277-298">The function [List.reduce](https://msdn.microsoft.com/library/048e1f95-691b-49cb-bb99-fb85f68f3d8b) is somewhat like `List.fold` and `List.scan`, except that instead of passing around a separate accumulator, `List.reduce` takes a function that takes two arguments of the element type instead of just one, and one of those arguments acts as the accumulator, meaning that it stores the intermediate result of the computation.</span></span> <span data-ttu-id="07277-299">`List.reduce`запускает обрабатывая первые два элемента списка, а затем использует результат операции вместе со следующим элементом.</span><span class="sxs-lookup"><span data-stu-id="07277-299">`List.reduce` starts by operating on the first two list elements, and then uses the result of the operation along with the next element.</span></span> <span data-ttu-id="07277-300">Так как здесь нет отдельного аккумулятора с собственным типом, функция `List.reduce` может использоваться вместо `List.fold` только в том случае, если аккумулятор и элемент имеют одинаковые типы.</span><span class="sxs-lookup"><span data-stu-id="07277-300">Because there is not a separate accumulator that has its own type, `List.reduce` can be used in place of `List.fold` only when the accumulator and the element type have the same type.</span></span> <span data-ttu-id="07277-301">В следующем коде показано использование функции `List.reduce`.</span><span class="sxs-lookup"><span data-stu-id="07277-301">The following code demonstrates the use of `List.reduce`.</span></span> <span data-ttu-id="07277-302">`List.reduce`создает исключение, если предоставленный список не содержит элементов.</span><span class="sxs-lookup"><span data-stu-id="07277-302">`List.reduce` throws an exception if the list provided has no elements.</span></span>

<span data-ttu-id="07277-303">В следующем коде первый вызов лямбда-выражения дает аргументы 2 и 4 и возвращает 6. В следующем вызове даются аргументы 6 и 10 и возвращается результат 16.</span><span class="sxs-lookup"><span data-stu-id="07277-303">In the following code, the first call to the lambda expression is given the arguments 2 and 4, and returns 6, and the next call is given the arguments 6 and 10, so the result is 16.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet33.fs)]
    
### <a name="converting-between-lists-and-other-collection-types"></a><span data-ttu-id="07277-304">Конвертация списков и другие типы коллекций</span><span class="sxs-lookup"><span data-stu-id="07277-304">Converting Between Lists and Other Collection Types</span></span>
<span data-ttu-id="07277-305">Модуль `List` предоставляет функции для прямой и обратной конвертации обоих последовательностей и массивов.</span><span class="sxs-lookup"><span data-stu-id="07277-305">The `List` module provides functions for converting to and from both sequences and arrays.</span></span> <span data-ttu-id="07277-306">Чтобы преобразовать в или из последовательности, используйте [List.toSeq](https://msdn.microsoft.com/library/7024be4b-ee70-43cc-8d0a-e6564a4ff7c0) или [List.ofSeq](https://msdn.microsoft.com/library/74ab9289-4a59-4433-92eb-3f662d7f7db0).</span><span class="sxs-lookup"><span data-stu-id="07277-306">To convert to or from a sequence, use [List.toSeq](https://msdn.microsoft.com/library/7024be4b-ee70-43cc-8d0a-e6564a4ff7c0) or [List.ofSeq](https://msdn.microsoft.com/library/74ab9289-4a59-4433-92eb-3f662d7f7db0).</span></span> <span data-ttu-id="07277-307">Для преобразования в или из массива используйте [List.toArray](https://msdn.microsoft.com/library/ac87dd82-a0cd-40b3-b1fa-dd3168134547) или [List.ofArray](https://msdn.microsoft.com/library/f4bddc26-8c8f-4307-a6d7-a49dceb97032).</span><span class="sxs-lookup"><span data-stu-id="07277-307">To convert to or from an array, use [List.toArray](https://msdn.microsoft.com/library/ac87dd82-a0cd-40b3-b1fa-dd3168134547) or [List.ofArray](https://msdn.microsoft.com/library/f4bddc26-8c8f-4307-a6d7-a49dceb97032).</span></span>


### <a name="additional-operations"></a><span data-ttu-id="07277-308">Дополнительные операции</span><span class="sxs-lookup"><span data-stu-id="07277-308">Additional Operations</span></span>
<span data-ttu-id="07277-309">Сведения о дополнительных операциях со списками, см. раздел справки по библиотеке [модуль Collections.List](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.list-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="07277-309">For information about additional operations on lists, see the library reference topic [Collections.List Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.list-module-%5bfsharp%5d).</span></span>


## <a name="see-also"></a><span data-ttu-id="07277-310">См. также</span><span class="sxs-lookup"><span data-stu-id="07277-310">See Also</span></span>
[<span data-ttu-id="07277-311">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="07277-311">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="07277-312">Типы языка F#</span><span class="sxs-lookup"><span data-stu-id="07277-312">F# Types</span></span>](fsharp-types.md)

[<span data-ttu-id="07277-313">Последовательности</span><span class="sxs-lookup"><span data-stu-id="07277-313">Sequences</span></span>](sequences.md)

[<span data-ttu-id="07277-314">Массивы</span><span class="sxs-lookup"><span data-stu-id="07277-314">Arrays</span></span>](arrays.md)

[<span data-ttu-id="07277-315">Параметры</span><span class="sxs-lookup"><span data-stu-id="07277-315">Options</span></span>](options.md)