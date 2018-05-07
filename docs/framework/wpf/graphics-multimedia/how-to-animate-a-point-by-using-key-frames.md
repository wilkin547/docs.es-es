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
ms.openlocfilehash: a59ceb62d7feb33d2cc8a747a7bfb85e551d785c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-animate-a-point-by-using-key-frames"></a>Cómo: Animar un punto mediante fotogramas clave
Este ejemplo muestra cómo utilizar el <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> clase para animar un <xref:System.Windows.Point>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se mueve una elipse a lo largo de un trazado triangular. El ejemplo se utiliza la <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> clase para animar la <xref:System.Windows.Media.EllipseGeometry.Center%2A> propiedad de un <xref:System.Windows.Media.EllipseGeometry>. Esta animación utiliza tres fotogramas clave de la siguiente manera:  
  
1.  Durante el primer medio segundo, utiliza una instancia de la <xref:System.Windows.Media.Animation.LinearPointKeyFrame> clase para mover la elipse a lo largo de una ruta de acceso a una velocidad constante desde su posición inicial. Al igual que los fotogramas clave lineales <xref:System.Windows.Media.Animation.LinearPointKeyFrame> crean una interpolación lineal suavizada entre los valores.  
  
2.  Durante el final de la siguiente medio segundo, utiliza una instancia de la <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> clase para mover repentinamente la elipse a lo largo de la ruta de acceso a la siguiente posición. Los fotogramas clave discretos como <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> crear saltos súbitos entre los valores.  
  
3.  Durante los últimos dos segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplinePointKeyFrame> clase para devolver la elipse a su posición inicial. Al igual que los fotogramas clave spline <xref:System.Windows.Media.Animation.SplinePointKeyFrame> crear una transición variable entre los valores según los valores de la <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> propiedad. En este ejemplo, la animación comienza despacio y se acelera exponencialmente hacia el final del segmento temporal.  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
 Para mantener la coherencia con otros ejemplos de animación, en las versiones de código de este ejemplo utiliza un <xref:System.Windows.Media.Animation.Storyboard> objeto que se va a aplicar el <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>. Sin embargo, al aplicar una animación única en código, es más fácil utilizar el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método en lugar de usar un <xref:System.Windows.Media.Animation.Storyboard>. Para obtener un ejemplo, vea [Animar una propiedad sin utilizar un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Media.EllipseGeometry>  
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Temas de procedimientos de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
