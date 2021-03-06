---
title: "События и обратные вызовы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 39dd4e31e84e455b72ce53bd8abffd650ce77dfc
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="events-and-callbacks"></a>События и обратные вызовы
Обратные вызовы являются точки расширения, обеспечивающие framework обратный вызов пользовательского кода в делегате. Эти делегаты обычно передаются в платформе через параметр типа метода.  
  
 События представляют собой особый случай обратных вызовов, поддерживает удобный и согласованное синтаксис для задания делегата (обработчиком событий). Кроме того завершение операторов и конструкторов Visual Studio содержат справку с помощью API-интерфейсов на основе событий. (См. [Разработка событий](../../../docs/standard/design-guidelines/event.md).)  
  
 **✓ Попробуйте** использования обратных вызовов, чтобы пользователи могли использовать пользовательский код, выполняемый средой.  
  
 **✓ Попробуйте** с помощью событий, чтобы разрешить пользователям настраивать поведение .NET framework без необходимости понимания объектно ориентированный проект.  
  
 **✓ СДЕЛАТЬ** предпочтение события простых обратных вызовов, поскольку они знакомы более широкому диапазону разработчиков и интегрированы с Visual Studio завершение операторов.  
  
 **X ИЗБЕГАЙТЕ** использования обратных вызовов в API, чувствительных к производительности.  
  
 **СДЕЛАТЬ ✓** использовать новую `Func<...>`, `Action<...>`, или `Expression<...>` типов вместо пользовательских делегатов, при определении обратными вызовами API-интерфейсы.  
  
 `Func<...>`и `Action<...>` представляют универсальных методов-делегатов. `Expression<...>`представляет определения функций, которые скомпилированы и впоследствии вызван во время выполнения, но может также быть сериализованы и передаются в удаленных процессов.  
  
 **СДЕЛАТЬ ✓** измерять и анализировать проблемы производительности с помощью `Expression<...>`, вместо использования `Func<...>` и `Action<...>` делегатов.  
  
 `Expression<...>`типы, в большинстве случаев логически эквивалентно `Func<...>` и `Action<...>` делегатов. Основное различие между ними является, что делегаты предназначены для использования в сценариях локального процесса; выражения, предназначены для случаев, когда он является полезным и невозможно вычислить значение выражения в удаленном процессе или компьютере.  
  
 **✓ СДЕЛАТЬ** понять, что путем вызова делегата, выполнения произвольного кода и который может иметь безопасности, правильность и совместимость.  
  
 *Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*  
  
 *Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*  
  
## <a name="see-also"></a>См. также  
 [Разработка с обеспечением расширяемости](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
