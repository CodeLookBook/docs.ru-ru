---
title: "Явная реализация интерфейса (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b746a69484b73a4212c729e02a1256ee1c83ea41
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="explicit-interface-implementation-c-programming-guide"></a>Явная реализация интерфейса (Руководство по программированию в C#)
Если [класс](../../../csharp/language-reference/keywords/class.md) реализует два интерфейса, содержащих член с одинаковой сигнатурой, при реализации такого члена в классе оба интерфейса будут использовать этот член в качестве собственной реализации. В следующем примере все вызовы `Paint` приводят к вызову одного и того же метода.  
  
 [!code-csharp[csProgGuideInheritance#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_1.cs)]  
  
 Если два члена [интерфейса](../../../csharp/language-reference/keywords/interface.md) выполняют разные функции, это может привести к некорректной реализации одного или обоих интерфейсов. Член интерфейса можно реализовать явно, создав член класса, который вызывается только через этот интерфейс и относится только к нему. Для этого в имени члена класса указывается имя интерфейса, после которого следует точка. Пример:  
  
 [!code-csharp[csProgGuideInheritance#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_2.cs)]  
  
 Член класса `IControl.Paint` доступен только через интерфейс `IControl`, а `ISurface.Paint` — только через интерфейс `ISurface`. Обе реализации метода будут разделены, и ни одна из них не будет доступна в классе напрямую. Пример:  
  
 [!code-csharp[csProgGuideInheritance#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_3.cs)]  
  
 Явная реализация также применяется в случаях, когда в каждом из двух интерфейсов объявляются разные члены (например, свойство и метод) с одинаковыми именами:  
  
 [!code-csharp[csProgGuideInheritance#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_4.cs)]  
  
 Чтобы реализовать оба интерфейса и избежать ошибок компилятора, класс должен использовать явную реализацию либо свойства P, либо метода P, либо одновременно обоих этих членов. Пример:  
  
 [!code-csharp[csProgGuideInheritance#43](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_5.cs)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [Интерфейсы](../../../csharp/programming-guide/interfaces/index.md)  
 [Наследование](../../../csharp/programming-guide/classes-and-structs/inheritance.md)
