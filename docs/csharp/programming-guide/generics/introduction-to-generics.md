---
title: "Введение в универсальные шаблоны. (Руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: generics [C#], about generics
ms.assetid: a1ad761e-42f7-41dd-a62f-452a2de26b9d
caps.latest.revision: "32"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 61baf26c9f942a59e3787ca55a2ac6a824410608
ms.sourcegitcommit: 3fd4e718d1bac9769fe0c1dd08ca1b2323ae272b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2018
---
# <a name="introduction-to-generics-c-programming-guide"></a>Введение в универсальные шаблоны. (Руководство по программированию на C#)
Универсальные классы и методы сочетают такие характеристики, как возможность многократного использования, типобезопасность и эффективность, которые не обеспечивают их неуниверсальные аналоги. Универсальные типы наиболее часто используются с коллекциями и методами, которые выполняют с ними операции. Библиотека классов на платформе .NET Framework 2.0 предоставляет новое пространство имен <xref:System.Collections.Generic>, которое содержит несколько новых универсальных классов коллекций. Во всех приложениях, предназначенных для [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 2.0 и более поздних версий, рекомендуется использовать новые универсальные классы коллекций вместо старых неуниверсальных аналогов, например <xref:System.Collections.ArrayList>. Дополнительные сведения см. в статье [Универсальные шаблоны в библиотеке классов платформы .NET Framework](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md).  
  
 Очевидно, вы можете создавать собственные универсальные типы и методы для предоставления собственных типобезопасных и эффективных обобщенных решений и шаблонов разработки. В следующем примере кода показан простой универсальный класс связанного списка для демонстрационных целей. (В большинстве случаев следует использовать класс <xref:System.Collections.Generic.List%601>, предоставляемый библиотекой классов .NET Framework, вместо создания собственного.) Параметр типа `T` используется в нескольких расположениях, где обычно используется конкретный тип для указания типа элемента, хранящегося в списке. Он используется в следующих случаях:  
  
-   в качестве типа параметра метода в методе `AddHead`;  
  
-   в качестве типа возвращаемого значения свойства `Data` во вложенном классе `Node`;  
  
-   в качестве типа закрытого члена `data` во вложенном классе.  
  
 Обратите внимание, что T доступен для вложенного класса `Node`. Когда экземпляр `GenericList<T>` создается с конкретным типом, например `GenericList<int>`, каждое вхождение `T` будет заменено `int`.  
  
 [!code-csharp[csProgGuideGenerics#2](../../../csharp/programming-guide/generics/codesnippet/CSharp/introduction-to-generics_1.cs)]  
  
 В следующем примере кода показано, как клиентский код использует универсальный класс `GenericList<T>` для создания списка целых чисел. Просто изменяя тип аргумента, следующий код можно легко изменить для создания списков строк или любого другого пользовательского типа:  
  
 [!code-csharp[csProgGuideGenerics#3](../../../csharp/programming-guide/generics/codesnippet/CSharp/introduction-to-generics_2.cs)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Collections.Generic>  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md)
