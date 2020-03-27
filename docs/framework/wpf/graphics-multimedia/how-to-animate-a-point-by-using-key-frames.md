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
ms.openlocfilehash: edcba36644cf78d6e98f934d9bd8b593af38b328
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344879"
---
# <a name="how-to-animate-a-point-by-using-key-frames"></a>Cómo: Animar un punto mediante fotogramas clave
En este ejemplo se <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> muestra cómo <xref:System.Windows.Point>utilizar la clase para animar un archivo .  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se mueve una elipse a lo largo de un trazado triangular. En el <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> ejemplo se <xref:System.Windows.Media.EllipseGeometry.Center%2A> utiliza la <xref:System.Windows.Media.EllipseGeometry>clase para animar la propiedad de un archivo . Esta animación utiliza tres fotogramas clave de la siguiente manera:  
  
1. Durante el primer medio segundo, <xref:System.Windows.Media.Animation.LinearPointKeyFrame> utiliza una instancia de la clase para mover la elipse a lo largo de una ruta a una velocidad constante desde su posición inicial. Los fotogramas <xref:System.Windows.Media.Animation.LinearPointKeyFrame> clave lineales como crean una interpolación lineal suave entre los valores.  
  
2. Durante el final del siguiente medio segundo, <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> utiliza una instancia de la clase para mover repentinamente la elipse a lo largo de la ruta de acceso a la siguiente posición. Los fotogramas <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> clave discretos, como crear saltos repentinos entre los valores.  
  
3. Durante los dos segundos finales, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplinePointKeyFrame> clase para mover la elipse de nuevo a su posición inicial. Los fotogramas <xref:System.Windows.Media.Animation.SplinePointKeyFrame> clave de spline como crean una <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> transición variable entre los valores según los valores de la propiedad. En este ejemplo, la animación comienza despacio y se acelera exponencialmente hacia el final del segmento temporal.  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
 Para mantener la coherencia con otros ejemplos de <xref:System.Windows.Media.Animation.Storyboard> animación, <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>las versiones de código de este ejemplo utilizan un objeto para aplicar el archivo . Sin embargo, al aplicar una sola animación en <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> el código, <xref:System.Windows.Media.Animation.Storyboard>es más sencillo usar el método en lugar de usar un archivo . Para obtener un ejemplo, vea [Animar una propiedad sin usar un guión gráfico](how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.EllipseGeometry>
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
- [Temas de procedimientos de fotogramas clave](key-frame-animation-how-to-topics.md)
