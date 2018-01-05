---
title: "Cómo: Animar un objeto Double mediante fotogramas clave"
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
helpviewer_keywords:
- Doubles [WPF], animating with key frames
- animation [WPF], Doubles with key frames
- key frames [WPF], animating Doubles with
ms.assetid: 3a1a7dba-7694-4907-8a2f-3408baebfa82
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e87717f6e2691142efa54a7e363f1038f8b74c1b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-double-by-using-key-frames"></a>Cómo: Animar un objeto Double mediante fotogramas clave
Este ejemplo muestra cómo animar el valor de una propiedad que toma un <xref:System.Double> mediante el uso de fotogramas clave.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se mueve un rectángulo por una pantalla. El ejemplo se utiliza la <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> clase para animar la <xref:System.Windows.Media.TranslateTransform.X%2A> propiedad de un <xref:System.Windows.Media.TranslateTransform> aplicado a un <xref:System.Windows.Shapes.Rectangle>. Esta animación, que se repite indefinidamente, utiliza tres fotogramas clave de la manera siguiente:  
  
1.  Durante los primeros tres segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> clase para mover el rectángulo a lo largo de una ruta de acceso a una velocidad constante desde su posición inicial hasta la posición 500. Al igual que los fotogramas clave lineales <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> crear una transición lineal suave entre valores.  
  
2.  Al final del cuarto segundo, utiliza una instancia de la <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> clase para mover repentinamente el rectángulo a la posición siguiente. Los fotogramas clave discretos como <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> crear saltos súbitos entre los valores. En este ejemplo, el rectángulo está en la posición inicial y aparece de pronto en la posición 500.  
  
3.  En los dos últimos segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> clase para devolver el rectángulo a su posición inicial. Al igual que los fotogramas clave spline <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> crear una transición variable entre los valores según el valor de la <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> propiedad. En este ejemplo, el rectángulo comienza a moverse despacio y se acelera exponencialmente hacia el final del segmento temporal.  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
 Para mantener la coherencia con otros ejemplos de animación, en las versiones de código de este ejemplo utiliza un <xref:System.Windows.Media.Animation.Storyboard> objeto que se va a aplicar el <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>. O bien, cuando se aplica una animación en código, es más fácil utilizar el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método en lugar de usar un <xref:System.Windows.Media.Animation.Storyboard>. Para obtener un ejemplo, vea [Animar una propiedad sin utilizar un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>  
 <xref:System.Windows.Shapes.Rectangle>  
 <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>  
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Temas de procedimientos de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
