---
title: "Наследование (F#)"
description: "Дополнительные сведения о определить отношения наследования F #, с помощью ключевого слова «inherit»."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: b38ab2f6-7ba7-4839-8eff-e6bd6cfd2b2f
ms.openlocfilehash: 331c8f4e39aacd9d5e55bfbaf584f037e58d36a1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="inheritance"></a>Наследование

Наследование, используемое для моделирования связи «is-a» или подтипов в объектно ориентированного программирования.


## <a name="specifying-inheritance-relationships"></a>Определение отношений наследования
Определить отношения наследования с помощью `inherit` ключевое слово в объявлении класса. В следующем примере показан Базовая синтаксическая форма.

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

Класс может иметь не более одного прямого базового класса. Если не указать базовый класс с помощью `inherit` ключевое слово, то класс неявно наследуется от `System.Object`.


## <a name="inherited-members"></a>Наследуемые члены
Если класс наследуется от другого класса, методы и члены базового класса доступны пользователям производного класса, как будто они являются непосредственными членами производного класса.

Все привязки let и параметры конструктора являются закрытыми для класса и, таким образом, нельзя обращаться из производных классов.

Ключевое слово `base` доступно в производных классах и относится к экземпляру базового класса. Он используется как идентификатор самого себя.


## <a name="virtual-methods-and-overrides"></a>Виртуальные методы и переопределение
Виртуальные методы (и свойства) работают иначе в F # по сравнению с другими языками .NET. Чтобы объявить новый виртуальный член, следует использовать `abstract` ключевое слово. Это делается независимо от того, может ли предоставлять реализацию по умолчанию для этого метода. Таким образом, полное определение виртуального метода в базовом классе имеет следующую структуру:

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

И в производном классе, переопределение данного виртуального метода имеет следующую структуру:

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

Если опустить реализацию по умолчанию в базовом классе, базовый класс становится абстрактным классом.

В следующем примере кода показано объявление нового виртуального метода `function1` в базовом классе и его можно переопределить в производном классе.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]
    
## <a name="constructors-and-inheritance"></a>Конструкторы и наследование
Необходимо вызвать конструктор базового класса в производном классе. Аргументы для конструктора базового класса отображаются в списке аргументов в `inherit` предложения. Используемые значения необходимо определять из аргументов, передаваемых в конструктор производного класса.

В следующем коде показано базовый класс и производный класс, в которых производного класса вызывает конструктор базового класса в выражении inherit:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

В случае несколько конструкторов можно использовать следующий код. Первая строка конструкторов в производных классах `inherit` предложение, а также поля отображаются как явные поля, объявленные с `val` ключевое слово. Дополнительные сведения см. в разделе [явные поля: `val` ключевое слово](members/explicit-fields-the-val-keyword.md).

```fsharp
type BaseClass =
    val string1 : string
    new (str) = { string1 = str }
    new () = { string1 = "" }

type DerivedClass =
    inherit BaseClass

    val string2 : string
    new (str1, str2) = { inherit BaseClass(str1); string2 = str2 }
    new (str2) = { inherit BaseClass(); string2 = str2 }

let obj1 = DerivedClass("A", "B")
let obj2 = DerivedClass("A")
```

## <a name="alternatives-to-inheritance"></a>Альтернативы для наследования
В случаях, где требуется незначительное изменение типа следует использовать выражение объекта вместо наследования. Следующий пример иллюстрирует использование выражения объекта в качестве альтернативы для создания нового производного типа:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

Дополнительные сведения о выражениях объектов см. в разделе [выражения объекта](object-expressions.md).

При создании иерархии объектов, рассмотрите возможность использования размеченного объединения вместо наследования. Размеченные объединения, можно моделировать изменение поведения различных объектов, имеющих общий тип. Использование одного размеченного объединения часто позволяет избавиться от необходимости для нескольких производных классов, которые незначительно отличаются друг от друга. Сведения о размеченные объединения см. в разделе [размеченные объединения](discriminated-unions.md).


## <a name="see-also"></a>См. также
[Выражения объекта](object-expressions.md)

[Справочник по языку F#](index.md)
