---
title: "Универсальные шаблоны (F#)"
description: "Универсальные шаблоны (F#)"
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: a9f2e2ee-bcb1-4ce3-8531-850aa183040f
translationtype: Human Translation
ms.sourcegitcommit: 0a01ec92a90d99fafaacbd3f71f5177e5cf94a68
ms.openlocfilehash: 98f65de4f3434aea9ee0b78848b85ba398543974
ms.lasthandoff: 04/05/2017

---

# <a name="generics"></a>Универсальные шаблоны

Значения функции, методы, свойства и агрегатные типы, например классы, записи и размеченные объединения, в F# могут быть *универсальными*. Универсальные конструкции содержат по меньшей мере один параметр типа, который обычно задается пользователем такой конструкции. Универсальные функции и типы позволяют писать код, который работает с множеством типов без повторения кода для каждого из них. В F# можно легко сделать код универсальным, так как зачастую код неявно определяется как универсальный механизмами определения типов и автоматического обобщения в компиляторе.


## <a name="syntax"></a>Синтаксис

```fsharp
// Explicitly generic function.
let function-name<type-parameters> parameter-list =
function-body

// Explicitly generic method.
[ static ] member object-identifer.method-name<type-parameters> parameter-list [ return-type ] =
method-body

// Explicitly generic class, record, interface, structure,
// or discriminated union.
type type-name<type-parameters> type-definition
```

## <a name="remarks"></a>Примечания
Объявления явно универсальной функции или явно универсального типа похоже на объявление неуниверсальных функций или типов, за исключением задания (и использования) параметров типа в угловых скобках после имени функции или типа.

Объявления часто являются неявно универсальными. Если вы не указываете полностью тип каждого параметра, составляющего функцию или тип, компилятор пытается определить тип каждого параметра, значения и переменной из написанного кода. Дополнительные сведения см. в статье [Определение типа](../type-inference.md). Если код для типа или функции не ограничивают типы параметров иным образом, то функция или тип являются неявно универсальными. Этот процесс называется *автоматическим обобщением*. Автоматическое обобщение имеет некоторые ограничения. Например, если компилятору F# не удается определить типы для универсальной конструкции, он выдает ошибку, ссылающуюся на ограничение под названием *ограничение значения*. В этом случае может потребоваться добавить некоторые заметки с типом. Дополнительные сведения об автоматическом обобщении и ограничении значения, а также об изменении кода для решения этой проблемы см. в статье [Автоматическое обобщение](automatic-generalization.md).

В приведенном выше синтаксисе *type-parameters* — это разделенный запятыми список параметров, представляющих неизвестные типы, каждый из которых начинается с одинарной кавычки. Может также присутствовать предложение ограничения, которое дополнительно ограничивает перечень допустимых типов для этого параметра типа. Синтаксис для различных предложений ограничения и прочие сведения об ограничениях см. в статье [Ограничения](constraints.md).

Компонент *type-definition* в синтаксисе совпадает с определением типа для неуниверсального типа. Он содержит параметры конструктора для типа класса, необязательное предложение `as`, символ равенства, поля записей, предложение `inherit`, варианты для размеченного объединения, привязки `let` и `do`, определения элементов и все остальное, что разрешено в определении неуниверсального типа.

Остальные компоненты синтаксиса являются такими же, что и в неуниверсальных функциях и типах. Например, *object-identifier* — это идентификатор, представляющий сам содержащий объект.

Свойства, поля и конструкторы не могут быть более универсальными, чем включающий тип. Кроме того, значения в модуле не могут быть универсальными.


## <a name="implicitly-generic-constructs"></a>Неявно универсальные конструкции
Когда компилятор F# определяет типы в коде, он автоматически рассматривает как универсальную любую функцию, которая может быть таковой. Если указать тип явно, например, тип параметра, автоматическое обобщение не выполняется.

В следующем примере кода `makeList` является универсальной, хотя ни она, ни ее параметры не объявляются явно как универсальные.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1700.fs)]

Подпись функции определяется как `'a -> 'a -> 'a list`. Обратите внимание, что `a` и `b` в этом примере определяются, как имеющие одинаковый тип. Это вызвано тем, что они включаются в список вместе, а все элементы списка должны иметь один тип.

Кроме того, функцию можно сделать универсальной, применив синтаксис с одинарной кавычкой в заметке типа, чтобы показать, что тип параметра является параметром универсального типа. В следующем коде `function1` является универсальной, так как ее параметры объявляются указанным образом — как параметры типа.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1701.fs)]
    
## <a name="explicitly-generic-constructs"></a>Явно универсальные конструкции
Вы также можете сделать функцию универсальной, явно объявив ее параметры типа в угловых скобках (`<type-parameter>`). Это проиллюстрировано в следующем коде.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1703.fs)]
    
## <a name="using-generic-constructs"></a>Использование универсальных конструкций
При использовании универсальных функций или методов вам может быть не нужно указывать аргументы типа. Компилятор использует определение типа для выведения подходящих аргументов типа. Если по-прежнему присутствует неоднозначность, можно указать аргументы типа в угловых скобках, разделяя их запятыми.

Следующий код показывает использование функций, определенных в предыдущих разделах.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1702.fs)]
    
>[!NOTE]
Сослаться на универсальный тип по имени можно двумя способами. Например, `list<int>` и `int list` представляют два способа сослаться на универсальный тип `list` с одним аргументом типа `int`. Последняя форма обычно используется только со встроенными типами F#, такими как `list` и `option`. При наличии нескольких аргументов типа обычно используется синтаксис `Dictionary<int, string>`, но можно также использовать синтаксис `(int, string) Dictionary`.

## <a name="wildcards-as-type-arguments"></a>Подстановочные знаки как аргументы типа
Чтобы указать, что аргумент типа должен определяться компилятором, можно использовать символ подчеркивания или подстановочный знак (`_`) вместо именованного аргумента типа. Это показано в приведенном ниже коде.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1704.fs)]
    
## <a name="constraints-in-generic-types-and-functions"></a>Ограничения в универсальных типах и функциях
В определении универсального типа или универсальной функции можно использовать только те конструкции, которые доступны для параметра универсального типа. Это необходимо для проверки вызовов функций и методов во время компиляции. Если вы объявляете параметры типа явно, можно применить к параметру универсального типа явное ограничение, чтобы уведомить компилятор о доступности некоторых методов и функций. Тем не менее, если разрешить компилятору F# выводить универсальные типы параметров, он самостоятельно определит подходящие ограничения. Дополнительные сведения см. в статье [Ограничения](constraints.md).


## <a name="statically-resolved-type-parameters"></a>Статически разрешаемые параметры типов
Существует два вида параметров типа, которые можно использовать в программах на языке F#. Первый — это параметры универсального типа, описанные в предыдущих разделах. Первый вид параметров типа эквивалентен параметрам универсального типа, которые используются в таких языках, как Visual Basic и C#. Другой вид параметров типа имеется только в F# и называется *статически разрешаемым параметром типа*. Сведения об этих конструкциях см. в статье [Статически разрешаемые параметры типов](statically-resolved-type-parameters.md).


## <a name="examples"></a>Примеры
[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1705.fs)]
    
## <a name="see-also"></a>См. также
[Справочник по языку](../index.md)

[Типы](../fsharp-types.md)

[Статически разрешаемые параметры типов](statically-resolved-type-parameters.md)

[Универсальные шаблоны в платформе .NET Framework](https://msdn.microsoft.com/library/ms172192.aspx)

[Автоматическое обобщение](automatic-generalization.md)

[Ограничения](constraints.md)