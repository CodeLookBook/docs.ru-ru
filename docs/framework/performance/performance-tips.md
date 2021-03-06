---
title: "Советы по производительности .NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- C# language, performance
- performance [C#]
- Visual Basic, performance
- performance [Visual Basic]
ms.assetid: ae275793-857d-4102-9095-b4c2a02d57f4
caps.latest.revision: "36"
author: BillWagner
ms.author: wiwagn
manager: wpickett
ms.workload: wiwagn
ms.openlocfilehash: 60c25de889e5055241486078baf46657b6870afd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="net-performance-tips"></a>Советы по производительности .NET
Под *производительностью* обычно понимается скорость выполнения программы. В некоторых случаях ее можно увеличить, следуя определенным основным правилам написания исходного кода. В некоторых программах важно тщательно проверить код и с помощью профилировщиков убедиться, что он выполняется максимально быстро. В других случаях такая оптимизация не требуется, поскольку код выполняется достаточно быстро в своем первоначальном виде. В этой статье описываются основные причины снижения производительности и приводятся рекомендации по ее повышению, а также ссылки на разделы с дополнительной информацией. Дополнительные сведения о планировании и измерении производительности см. в разделе [Производительность](../../../docs/framework/performance/index.md)  
  
## <a name="boxing-and-unboxing"></a>Упаковка–преобразование и распаковка–преобразование  
 Не рекомендуется использовать типы значений в тех случаях, где они многократно упаковываются, например в классах неуниверсальных коллекций, таких как <xref:System.Collections.ArrayList?displayProperty=nameWithType>. Чтобы избежать упаковки типов значений, используйте универсальные коллекции, такие как <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>. Операции упаковки и распаковки являются весьма затратными процессами с точки зрения вычислений. При упаковке типа значений создается полностью новый объект. Это может занимать почти в 20 раз больше времени, чем простое присваивание ссылки. Процесс приведения при распаковке также занимает в 4 раза больше времени, чем присваивание. Дополнительные сведения см. в разделе [Упаковка-преобразование и распаковка-преобразование](~/docs/csharp/programming-guide/types/boxing-and-unboxing.md).  
  
## <a name="strings"></a>Строки  
 При сцеплении большого числа строковых переменных, например в непрерывном цикле, используйте <xref:System.Text.StringBuilder?displayProperty=nameWithType> вместо [оператора + (C#)](~/docs/csharp/language-reference/operators/addition-operator.md) или [операторов сцепления (Visual Basic)](~/docs/visual-basic/language-reference/operators/concatenation-operators.md). Дополнительные сведения см. в разделах [Практическое руководство. Сцепка нескольких строк](~/docs/csharp/programming-guide/strings/how-to-concatenate-multiple-strings.md) и [Операторы объединения в Visual Basic](~/docs/visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md).  
  
## <a name="destructors"></a>Деструкторы  
 Пустые деструкторы использовать не следует. Если класс содержит деструктор, то в очереди метода Finalize создается запись. При вызове деструктора вызывается сборщик мусора, выполняющий обработку очереди. Если деструктор пустой, это приводит только к ненужному снижению производительности. Дополнительные сведения см. в разделах [Деструкторы](~/docs/csharp/programming-guide/classes-and-structs/destructors.md) и [Время существования: создание и уничтожение объектов](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
## <a name="other-resources"></a>Другие ресурсы  
  
-   [Повышение производительности управляемого кода](http://go.microsoft.com/fwlink/?LinkId=99294)  
  
-   [Повышение производительности управляемых приложений: учебник для начинающих](http://go.microsoft.com/fwlink/?LinkId=99295)  
  
-   [Общие сведения о сборке мусора и советы по повышению производительности](http://go.microsoft.com/fwlink/?LinkId=99296)  
  
-   [Советы и рекомендации по повышению производительности в приложениях .NET](http://go.microsoft.com/fwlink/?LinkId=99297)  
  
-   [Внутреннее устройство средств диагностики для .NET](http://go.microsoft.com/fwlink/?LinkId=112407)  
  
-   [Советы по повышению производительности от Рико Мариани](http://go.microsoft.com/fwlink/?LinkId=115679)  
  
## <a name="see-also"></a>См. также  
 [Производительность](../../../docs/framework/performance/index.md)  
 [Основные понятия программирования](http://msdn.microsoft.com/library/65c12cca-af4f-4017-886e-2dbc00a189d6)  
 [Руководство по программированию на Visual Basic](../../visual-basic/programming-guide/index.md)  
 [Руководство по программированию на C#](http://msdn.microsoft.com/library/ac0f23a2-6bf3-4077-be99-538ae5fd3bc5)
