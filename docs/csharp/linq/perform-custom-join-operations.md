---
title: "Выполнение пользовательских операций соединения"
description: "Сведения о выполнении пользовательских операций соединения."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 56a2a4a5-7299-497d-b3c3-23c848678911
ms.openlocfilehash: fef146c92a5cbbf21f8f1688f221c2bd45c99de7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="perform-custom-join-operations"></a>Выполнение пользовательских операций соединения

В этом примере показано, как выполнить операции соединения, которые нельзя осуществить с помощью предложения `join`. В выражении запроса предложение `join` ограничено уравнивающими соединениями и оптимизировано для них; они являются самым общим типом операций соединения. При выполнении уравнивающего соединения использование предложения `join` почти всегда обеспечивает наилучшую производительность.  
  
 Однако предложение `join` нельзя использовать в указанных ниже случаях.  
  
-   Соединение объявлено в выражении неравенства (не уравнивающее соединение).  
  
-   Соединение объявлено в нескольких выражениях равенства или неравенства.  
  
-   Необходимость создания временной переменной диапазона для правосторонней (внутренней) последовательности перед операцией соединения.  
  
 Чтобы независимо представить каждый источник данных при выполнении соединений, не являющихся уравнивающими, можно использовать несколько предложений `from`. Затем к переменной диапазона для каждого источника можно применить выражение предиката в предложении `where`. Выражение также может принимать форму вызова метода.  
  
> [!NOTE]
>  Не путайте этот вид пользовательской операции соединения с использованием нескольких предложений `from` для доступа к внутренним коллекциям. Дополнительные сведения см. в разделе [Предложение join](../language-reference/keywords/join-clause.md).  
  
## <a name="example"></a>Пример  
 Первый метод в приведенном ниже примере показывает простое перекрестное соединение. Перекрестные соединения следует использовать с осторожностью, так как они могут возвращать очень большие наборы результатов. Однако такие соединения могут быть полезны при создании исходных последовательностей, относительно которых выполняются дополнительные запросы.  
  
 Результатом второго метода является последовательность всех продуктов, идентификатор категории которых находится в списке категорий с правой стороны. Учтите необходимость использования предложения `let` и метода `Contains` для создания временного массива. Также можно создать массив перед запросом и удалить первое предложение `from`.  
  
 [!code-csharp[csProgGuideLINQ#64](../../../samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_1.cs)]  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере запрос должен соединять две последовательности на основе сопоставления ключей, которые в случае с внутренней (правосторонней) последовательностью не могут быть получены до предложения соединения. Если соединение было выполнено с предложением `join`, для каждого элемента требуется вызвать метод `Split`. Использование нескольких предложений `from` позволяет запросу избежать издержек, связанных с повторным вызовом метода. Однако поскольку предложение `join` оптимизировано, в этом случае его использование может быть эффективнее нескольких предложений `from`. Результаты будут зависеть в основном от затрат на вызов метода.  
  
 [!code-csharp[csProgGuideLINQ#13](../../../samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_2.cs)]  
  
## <a name="see-also"></a>См. также  
 [Выражения запросов LINQ](index.md)  
 [предложение join](../language-reference/keywords/join-clause.md)  
 [Упорядочение результатов предложения соединения](order-the-results-of-a-join-clause.md)
