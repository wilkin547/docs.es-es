---
title: "Cómo: Animar el grosor de un borde mediante fotogramas clave"
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
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a>Cómo: Animar el grosor de un borde mediante fotogramas clave
Este ejemplo muestra cómo animar la <xref:System.Windows.Controls.Control.BorderThickness%2A> propiedad de un <xref:System.Windows.Controls.Border>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> clase para animar la <xref:System.Windows.Controls.Control.BorderThickness%2A> propiedad de un <xref:System.Windows.Controls.Border>. Esta animación utiliza tres fotogramas clave de la siguiente manera:  
  
1.  Durante el primer medio segundo, utiliza una instancia de la <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> clase para aumentar gradualmente el grosor del borde. El ejemplo se utiliza <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> para crear un aumento lineal suave entre valores.  
  
2.  Al final de la siguiente medio segundo, utiliza una instancia de la <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> clase para aumentar el grosor del borde de repente. Los fotogramas clave discretos como las que se derivan de <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> crean saltos súbitos entre valores, es decir, el movimiento de la animación es irregular.  
  
3.  Durante los últimos dos segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> clase para reducir el grosor del borde. Los fotogramas clave spline como las que se derivan de <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> crear una transición variable entre los valores según los valores de la <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> propiedad. En este fotograma clave, la animación se inicia lentamente y se va acelerando de forma exponencial hacia el final del segmento temporal.  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>  
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Temas de procedimientos de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)  
 [Animar el valor del grosor de un borde](../../../../docs/framework/wpf/controls/how-to-animate-a-borderthickness-value.md)
