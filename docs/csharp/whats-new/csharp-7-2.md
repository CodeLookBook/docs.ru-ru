---
title: "Новые возможности C# 7.2"
description: "Обзор новых возможностей в C# 7.2."
keywords: "Разработка языка C#, версия 7.2, Visual Studio 2017"
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: 9e7fefde6763dbd5c73c01e45e5652d9f207c213
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2018
---
# <a name="whats-new-in-c-72"></a>Новые возможности C# 7.2

В очередной версии C# 7.2 реализован ряд новых полезных возможностей.
Одной из основных задач этого выпуска стало повышение эффективности работы с типами значений за счет исключения избыточных операций копирования и выделения памяти. 

Остальные нововведения реализованы преимущественно для удобства.

В C# 7.2 предусмотрен элемент управления [выбором версии языка](csharp-7-1.md#language-version-selection), с помощью которого можно задать версию языка компилятора.

Новые языковые функции в этом выпуске

* [Семантика ссылок с типами значений](#reference-semantics-with-value-types)
  - Ряд улучшений синтаксиса, обеспечивающих работу с типами значений с использованием семантики ссылок.
* [Неконечные именованные аргументы](#non-trailing-named-arguments)
  - После именованных аргументов могут следовать позиционные аргументы.
* [Начальные символы подчеркивания в числовых литералах](#leading-underscores-in-numeric-literals)
  - Перед любыми печатными знаками в числовых литералах теперь могут использоваться начальные знаки подчеркивания.
* [Модификатор доступа `private protected`](#private-protected)
  - Модификатор доступа `private protected` разрешает доступ для производных классов в одной сборке.

## <a name="reference-semantics-with-value-types"></a>Семантика ссылок с типами значений

Представленные в версии 7.2 языковые функции обеспечивают работу с типами значений с использованием семантики ссылок. Благодаря этому удается повысить производительность за счет использования минимального числа операций копирования типов значений без выделения памяти в связи с применением ссылочных типов. В число новых возможностей входят:

 - модификатор `in` для параметров, указывающий, что аргумент передается по ссылке, но не изменяется вызываемым методом;
 - модификатор `ref readonly` для возвращаемого значения метода, указывающий, что метод возвращает значение по ссылке, но не допускает операции записи в соответствующий объект;
 - объявление `readonly struct`, указывающее, что структура является неизменяемой и должна передаваться в методы члена как параметр `in`;
 - объявление `ref struct`, указывающее, что тип структуры обращается напрямую к управляемой памяти и всегда должен обрабатываться с выделением стека.

Дополнительные сведения об этих изменениях см. в разделе [Использование типов значений с семантикой ссылок](../reference-semantics-with-value-types.md).

## <a name="non-trailing-named-arguments"></a>Неконечные именованные аргументы

В вызовах методов после находящихся в правильной позиции именованных аргументов теперь можно использовать позиционные аргументы. Дополнительные сведения см. в разделе [Именованные и необязательные аргументы](../programming-guide/classes-and-structs/named-and-optional-arguments.md).

## <a name="leading-underscores-in-numeric-literals"></a>Начальные символы подчеркивания в числовых литералах

Из-за того, как в версии C# 7.0 была реализована поддержка разделителей между знаками, в качестве первого знака в значении литерала нельзя было использовать символ `_`. Теперь шестнадцатеричные и двоичные числовые литералы могут начинаться со знака `_`. 

Пример:

```csharp
int binaryValue = 0b_0101_0101;
```

## <a name="private-protected-access-modifier"></a>_private protected_ — модификатор доступа

Также представлен новый составной модификатор доступа `private protected`, указывающий, что доступ к члену может осуществляться содержащим классом или производными классами, которые объявлены в рамках одной сборки. В отличие от модификатора `protected internal`, который разрешает доступ производным классам или классам из той же сборки, `private protected` ограничивает доступ только для производных классов, объявленных в рамках одной сборки.

Дополнительные сведения см. в разделе [Модификаторы доступа](../language-reference/keywords/access-modifiers.md) в справочнике по языку.
