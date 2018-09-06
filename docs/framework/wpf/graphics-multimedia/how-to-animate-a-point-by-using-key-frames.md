---
title: 'Cómo: Animar un punto mediante fotogramas clave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating Points with
- Points [WPF], animating with key frames
- animation [WPF], Points with key frames
ms.assetid: d2e2ef10-0773-4133-856e-d41c09f60ded
ms.openlocfilehash: c2fd8c6c6fd84bbfd6d56f573588d7204249f31d
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43857406"
---
# <a name="how-to-animate-a-point-by-using-key-frames"></a>Cómo: Animar un punto mediante fotogramas clave
En este ejemplo se muestra cómo usar el <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> clase para animar un <xref:System.Windows.Point>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se mueve una elipse a lo largo de un trazado triangular. El ejemplo se usa el <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> clase se va a animar el <xref:System.Windows.Media.EllipseGeometry.Center%2A> propiedad de un <xref:System.Windows.Media.EllipseGeometry>. Esta animación utiliza tres fotogramas clave de la siguiente manera:  
  
1.  Durante el primer medio segundo, utiliza una instancia de la <xref:System.Windows.Media.Animation.LinearPointKeyFrame> clase para mover la elipse a lo largo de una ruta de acceso a un ritmo constante desde su posición inicial. Los fotogramas clave lineales como <xref:System.Windows.Media.Animation.LinearPointKeyFrame> crean una interpolación lineal suave entre valores.  
  
2.  Durante el fin de la siguiente medio segundo, utiliza una instancia de la <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> clase para mover repentinamente la elipse a lo largo de la ruta de acceso a la siguiente posición. Los fotogramas clave discretos como <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> crean saltos súbitos entre los valores.  
  
3.  Durante los dos últimos segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplinePointKeyFrame> clase para devolver la elipse a su posición inicial. Los fotogramas clave spline como <xref:System.Windows.Media.Animation.SplinePointKeyFrame> crean una transición variable entre los valores según los valores de la <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> propiedad. En este ejemplo, la animación comienza despacio y se acelera exponencialmente hacia el final del segmento temporal.  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
 Para mantener la coherencia con otros ejemplos de animación, las versiones de código de este ejemplo utiliza un <xref:System.Windows.Media.Animation.Storyboard> objeto al que aplicar el <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>. Sin embargo, al aplicar una animación única en código, resulta más fácil de usar el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método en lugar de usar un <xref:System.Windows.Media.Animation.Storyboard>. Para obtener un ejemplo, vea [Animar una propiedad sin utilizar un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Media.EllipseGeometry>  
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Temas de procedimientos de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
