---
title: "Взаимодействие с неуправляемым кодом"
ms.date: 01/17/2018
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords:
- unmanaged code, interoperation
- managed code, interoperation with unmanaged code
- .NET Framework, interoperation with unmanaged code
- unmanaged code
- interoperation with unmanaged code
- interoperation with unmanaged code, about interoperation
- components [.NET Framework], interoperation with unmanaged code
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 38c569633304ed9e6f86e7a04ef7b0dfa79b6704
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="interoperating-with-unmanaged-code"></a>Взаимодействие с неуправляемым кодом

Платформа .NET Framework обеспечивает взаимодействие с COM-компонентами, службами COM+, внешними библиотеками типов и многими службами операционной системы. Типы данных, подписи методов и механизмы обработки ошибок различны в управляемой и неуправляемой моделях объектов. Для упрощения взаимодействия между компонентами .NET Framework и неуправляемым программным кодом, а также для облегчения перехода от одной модели к другой среда CLR скрывает имеющиеся в этих объектных моделях различия от клиентов и серверов.

Код, выполняющийся под управлением среды выполнения, называется управляемым кодом. И наоборот, код, выполняемый вне среды выполнения, называется неуправляемым кодом. Примерами неуправляемого кода являются компоненты COM, интерфейсы ActiveX и функции Win32 API.

## <a name="in-this-section"></a>Содержание раздела

[Предоставление COM-компонентов платформе .NET Framework](exposing-com-components.md)  
Описывает способы использования COM-компонентов в приложениях .NET Framework.

[Предоставление компонентов .NET Framework клиентам COM](exposing-dotnet-components-to-com.md)  
Описывает способы использования компонентов .NET Framework в приложениях COM.

[Использование неуправляемых функций DLL](consuming-unmanaged-dll-functions.md)  
Описывает способ вызова неуправляемых функций DLL с помощью вызова платформы.

[Маршалинг взаимодействия](interop-marshaling.md)  
Описывается маршалинг для COM-взаимодействия и вызова платформы.

[Практическое руководство. Сопоставление значений HRESULT и исключений](how-to-map-hresults-and-exceptions.md)  
Описывает сопоставление исключений и значений HRESULT.

[Oболочки COM](com-wrappers.md)  
Описывает оболочки, предоставляемые COM-взаимодействия.

[Эквивалентность типов и внедренные типы взаимодействия](type-equivalence-and-embedded-interop-types.md)  
Описывает, как внедренного сведений о типах COM в сборках, и как общеязыковая среда выполнения определяет эквивалентность встроенных типов COM.

[Практическое руководство. Создание основной сборки взаимодействия с помощью программы Tlbimp.exe](how-to-generate-primary-interop-assemblies-using-tlbimp-exe.md)  
Описывает способ создания основных сборок взаимодействия с помощью *Tlbimp.exe* (программа импорта библиотек типов).

[Практическое руководство. Регистрация основных сборок взаимодействия](how-to-register-primary-interop-assemblies.md)  
В этой статье описывается регистрация основных сборок взаимодействия, прежде чем на них можно сослаться в проектах.

[COM-взаимодействие без регистрации](registration-free-com-interop.md)  
Описывает, как COM-взаимодействия активации компонентов без использования реестра Windows.

[Практическое руководство. Настройка COM-компонентов на основе платформы .NET Framework для активации без регистрации](configure-net-framework-based-com-components-for-reg.md)  
Описывает способ создания манифеста приложения и для создания и внедрения манифеста компонента.
