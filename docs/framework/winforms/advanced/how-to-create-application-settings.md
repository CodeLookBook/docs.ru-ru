---
title: "Практическое руководство. Создание параметров приложения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application settings [Windows Forms], Windows Forms
- application settings [Windows Forms], creating
ms.assetid: 1e7aa347-af75-41e5-89ca-f53cab704f72
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6d0ede88d8f9b4c15cd3e0f141870b9a5e747aa9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-application-settings"></a>Практическое руководство. Создание параметров приложения
С помощью управляемого кода можно создавать параметры приложения и привязывать их к свойствам формы или ее элементов управления, чтобы эти параметры загружались и сохранялись автоматически во время выполнения.  
  
 В представленной ниже процедуре вручную создается класс-оболочка, производный от класса <xref:System.Configuration.ApplicationSettingsBase>. К этому классу добавляется открытое свойство для каждого параметра приложения, который требуется предоставить.  
  
 Эту процедуру можно также выполнить с помощью минимального объема кода в конструкторе Visual Studio.  См. также [как: Создание параметров приложения с помощью конструктора](http://msdn.microsoft.com/library/wabtadw6\(v=vs.110\)).  
  
### <a name="to-create-new-application-settings-programmatically"></a>Создание параметров приложения программными средствами  
  
1.  Добавьте в проект новый класс и переименуйте его. Для выполнения этой процедуры вызовет этот класс `MyUserSettings`. Измените определение класса так, чтобы он стал производным от <xref:System.Configuration.ApplicationSettingsBase>.  
  
2.  Определите в этом классе-оболочке свойство для каждого требуемого параметра приложения и примените его с атрибутом <xref:System.Configuration.ApplicationScopedSettingAttribute> или <xref:System.Configuration.UserScopedSettingAttribute> в зависимости от области действия параметра. Дополнительные сведения об области параметров см. в разделе [Общие сведения о параметрах приложения](../../../../docs/framework/winforms/advanced/application-settings-overview.md). На этом этапе код должен выглядеть так:  
  
     [!code-csharp[ApplicationSettings.Create#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
     [!code-vb[ApplicationSettings.Create#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]  
  
3.  Создайте экземпляр этого класса-оболочки в приложении. Как правило, он является закрытым членом главной формы. Определив класс, нужно привязать его к свойству, в данном случае к свойству <xref:System.Windows.Forms.Form.BackColor%2A> формы. Это можно сделать на форме `Load` обработчика событий.  
  
     [!code-csharp[ApplicationSettings.Create#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/Form1.cs#2)]
     [!code-vb[ApplicationSettings.Create#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/Form1.vb#2)]  
  
4.  Если вы предоставляете возможность изменения параметров во время выполнения, необходимо сохранять текущие параметры пользователя на диск при закрытии формы, иначе изменения будут потеряны.  
  
     [!code-csharp[ApplicationSettings.Create#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/Form1.cs#3)]
     [!code-vb[ApplicationSettings.Create#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/Form1.vb#3)]  
  
     Теперь новый параметр приложения успешно создан и связан с указанным свойством.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Поставщик параметров по умолчанию, <xref:System.Configuration.LocalFileSettingsProvider>, сохраняет сведения в файлах конфигурации в виде обычного текста. В результате безопасность зависит от уровня разрешений на доступ к файлу, предоставляемого операционной системой текущему пользователю. Поэтому при хранении информации в файлах конфигурации необходимо соблюдать осторожность. Например, параметры приложения часто используются для хранения строк подключений, которые указывают на хранилище данных приложения. Однако в целях безопасности в таких строках не должны содержаться пароли. Подробнее о строках подключения см. в разделе <xref:System.Configuration.SpecialSetting>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Configuration.SpecialSettingAttribute>  
 <xref:System.Configuration.LocalFileSettingsProvider>  
 [Общие сведения о параметрах приложений](../../../../docs/framework/winforms/advanced/application-settings-overview.md)  
 [Практическое руководство. Проверка параметров приложения](../../../../docs/framework/winforms/advanced/how-to-validate-application-settings.md)
