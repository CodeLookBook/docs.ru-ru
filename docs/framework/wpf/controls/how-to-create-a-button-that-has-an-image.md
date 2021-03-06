---
title: "Практическое руководство. Создание кнопки, содержащей изображение"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: Button controls [WPF], creating
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e95f027a8e3568365fa7957c36241b6ec2c30d28
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-button-that-has-an-image"></a>Практическое руководство. Создание кнопки, содержащей изображение
В этом примере показано, как включить изображение в <xref:System.Windows.Controls.Button>.  
  
## <a name="example"></a>Пример  
 В следующем примере создается два <xref:System.Windows.Controls.Button> элементов управления. Один <xref:System.Windows.Controls.Button> содержит текст, а другой изображения. Изображение находится в папке Data, которая вложена в папку проекта этого примера. Когда пользователь щелкает <xref:System.Windows.Controls.Button> , содержащее изображения, фон и текст другого <xref:System.Windows.Controls.Button> изменения.  
  
 В этом примере создается <xref:System.Windows.Controls.Button> элементы управления с помощью разметки, но использует код, записываемый <xref:System.Windows.Controls.Primitives.ButtonBase.Click> обработчики событий.  
  
 [!code-xaml[BtnColor#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## <a name="see-also"></a>См. также  
 [Элементы управления](../../../../docs/framework/wpf/controls/index.md)  
 [Библиотека элементов управления](../../../../docs/framework/wpf/controls/control-library.md)
