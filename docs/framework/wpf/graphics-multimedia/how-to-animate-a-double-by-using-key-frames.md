---
title: 'Cómo: Animar un objeto Double mediante fotogramas clave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Doubles [WPF], animating with key frames
- animation [WPF], Doubles with key frames
- key frames [WPF], animating Doubles with
ms.assetid: 3a1a7dba-7694-4907-8a2f-3408baebfa82
ms.openlocfilehash: 9eab794cc8411230226cddc97beaa13c1bdd9405
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344934"
---
# <a name="how-to-animate-a-double-by-using-key-frames"></a>Cómo: Animar un objeto Double mediante fotogramas clave
En este ejemplo se muestra cómo animar <xref:System.Double> el valor de una propiedad que toma una mediante fotogramas clave.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se mueve un rectángulo por una pantalla. En el <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> ejemplo se <xref:System.Windows.Media.TranslateTransform.X%2A> utiliza la <xref:System.Windows.Media.TranslateTransform> clase <xref:System.Windows.Shapes.Rectangle>para animar la propiedad de un archivo . Esta animación, que se repite indefinidamente, utiliza tres fotogramas clave de la manera siguiente:  
  
1. Durante los primeros tres segundos, <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> utiliza una instancia de la clase para mover el rectángulo a lo largo de un trazado a una velocidad constante desde su posición inicial hasta la posición 500. Los fotogramas <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> clave lineales como crean una transición lineal suave entre los valores.  
  
2. Al final del cuarto segundo, utiliza <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> una instancia de la clase para mover repentinamente el rectángulo a la siguiente posición. Los fotogramas <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> clave discretos, como crear saltos repentinos entre los valores. En este ejemplo, el rectángulo está en la posición inicial y aparece de pronto en la posición 500.  
  
3. En los últimos dos segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> clase para mover el rectángulo a su posición inicial. Los fotogramas <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> clave de spline como crean una <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> transición variable entre valores según el valor de la propiedad. En este ejemplo, el rectángulo comienza a moverse despacio y se acelera exponencialmente hacia el final del segmento temporal.  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
 Para mantener la coherencia con otros ejemplos de <xref:System.Windows.Media.Animation.Storyboard> animación, <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>las versiones de código de este ejemplo utilizan un objeto para aplicar el archivo . Como alternativa, al aplicar una sola animación en el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> código, es <xref:System.Windows.Media.Animation.Storyboard>más sencillo usar el método en lugar de usar un archivo . Para obtener un ejemplo, vea [Animar una propiedad sin usar un guión gráfico](how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Shapes.Rectangle>
- <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>
- <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
- [Temas de procedimientos de fotogramas clave](key-frame-animation-how-to-topics.md)
