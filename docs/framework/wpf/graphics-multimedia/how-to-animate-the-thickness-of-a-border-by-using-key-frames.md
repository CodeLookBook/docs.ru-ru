---
title: "Инструкция по Анимации толщины границы с помощью ключевых кадров"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0f255ff38ec7ee79f02a0cd40a3f0143c36e1c58
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a>Инструкция по Анимации толщины границы с помощью ключевых кадров
В этом примере демонстрируется анимация <xref:System.Windows.Controls.Control.BorderThickness%2A> свойство <xref:System.Windows.Controls.Border>.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> класса для анимации <xref:System.Windows.Controls.Control.BorderThickness%2A> свойство <xref:System.Windows.Controls.Border>. Эта анимация использует три ключевых кадра следующим образом:  
  
1.  Во время первого полсекунды используется экземпляр <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> класса для постепенного увеличения толщины границы. В этом примере <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> Создание smooth линейного увеличения между значениями.  
  
2.  В конце следующей половины секунды используется экземпляр <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> класса для мгновенного увеличения толщины границы. Дискретные опорные кадры как производный от <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> создают резкие переходы между значениями, то есть, перемещение анимации рывками.  
  
3.  В течение последних двух секунд используется экземпляр <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> класса для уменьшения толщины границы. Опорных кадров сплайна как производный от <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> создания переменного перехода между значениями согласно значениям <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> свойство. В этом опорном кадре анимация начинается медленно и экспоненциально ускоряется к концу временного сегмента.  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>  
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Практические руководства, посвященные анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)  
 [Анимирование значения BorderThickness](../../../../docs/framework/wpf/controls/how-to-animate-a-borderthickness-value.md)
