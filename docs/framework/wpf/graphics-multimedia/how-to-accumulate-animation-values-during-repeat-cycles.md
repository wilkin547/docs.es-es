---
title: "Cómo: Acumular valores de animaciones durante la repetición de ciclos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- accumulating animation values across repeating cycles [WPF]
- animation [WPF], accumulating values across repeating cycles
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4abe19f4548ed41eb19ae4dffb37b832a7df71d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-accumulate-animation-values-during-repeat-cycles"></a>Cómo: Acumular valores de animaciones durante la repetición de ciclos
Este ejemplo muestra cómo utilizar el <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> propiedad que se va a acumular valores de animaciones entre ciclos que se repiten.  
  
## <a name="example"></a>Ejemplo  
 Use la <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> propiedad que se va a acumular los valores base de una animación entre ciclos que se repiten. Por ejemplo, si establece una animación se repita 9 veces (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9 x") y establezca la propiedad que se va a animar entre 10 y 15 (From = 10 To = 15), la propiedad se anima de 10 a 15 durante el primer ciclo, de 15 a 20 durante el segundo ciclo , de 20 a 25 durante el tercer ciclo y así sucesivamente. Por lo tanto, cada ciclo de animación usa el valor de animación final del ciclo de animación anterior como su valor base.  
  
 Puede usar el `IsCumulative` propiedad con animaciones más básicas y la mayoría de las animaciones de fotograma clave. Para obtener más información, consulte [información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) y [información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
 En el ejemplo siguiente se muestra este comportamiento al animar el ancho de cuatro rectángulos. En el ejemplo:  
  
-   Anima el primer rectángulo con <xref:System.Windows.Media.Animation.DoubleAnimation> y establece la <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> propiedad `true`.  
  
-   Anima el segundo rectángulo con <xref:System.Windows.Media.Animation.DoubleAnimation> y establece la <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> propiedad en el valor predeterminado de `false`.  
  
-   Anima el tercer rectángulo con <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> y establece la <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> propiedad `true`.  
  
-   Anima el último rectángulo con <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> y establece la <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> propiedad `false`.  
  
 [!code-xaml[timingbehaviors_snip#IsCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## <a name="see-also"></a>Vea también  
 [Agregar un valor de salida de animación a un valor inicial de animación](../../../../docs/framework/wpf/graphics-multimedia/how-to-add-an-animation-output-value-to-an-animation-starting-value.md)  
 [Repetir una animación](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md)  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Temas de procedimientos](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
