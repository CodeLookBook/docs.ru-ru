---
title: "Практическое руководство. Интерактивное использование свойства Spring в элементе управления StatusStrip"
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
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
- status bars [Windows Forms], examples
- Spring property [Windows Forms]
ms.assetid: 18bde842-a93c-48dd-9db3-15738a1775ce
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c642b0c4cb2313d04bdca00294af791847e68c76
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-spring-property-interactively-in-a-statusstrip"></a>Практическое руководство. Интерактивное использование свойства Spring в элементе управления StatusStrip
Для размещения элемента управления <xref:System.Windows.Forms.ToolStripStatusLabel> в элементе <xref:System.Windows.Forms.StatusStrip> можно использовать свойство <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>. Свойство <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> определяет, заполняет ли элемент управления <xref:System.Windows.Forms.ToolStripStatusLabel> доступное пространство в элементе управления <xref:System.Windows.Forms.StatusStrip> автоматически.  
  
## <a name="example"></a>Пример  
 В примере кода ниже показано использование свойства <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> для размещения элемента управления <xref:System.Windows.Forms.ToolStripStatusLabel> в элементе <xref:System.Windows.Forms.StatusStrip>. Для переключения значения свойства <xref:System.Windows.Forms.ToolStripItem.Click> обработчик событий <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> выполняет исключающую операцию ИЛИ (XOR).  
  
 Чтобы использовать этот пример кода, скомпилируйте и запустите приложение и нажмите кнопку **Middle (Spring)** на <xref:System.Windows.Forms.StatusStrip> переключите значение <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> свойства.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#50)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#50)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System.Design, System.Drawing и System.Windows.Forms.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [Построение из командной строки с помощью файла csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], можно также вставить код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 <xref:System.Windows.Forms.StatusStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [Элемент управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
