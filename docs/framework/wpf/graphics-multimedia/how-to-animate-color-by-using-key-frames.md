---
title: 'Cómo: Animar un color mediante fotogramas clave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
ms.openlocfilehash: 8a444706f7541b52722ab8257a88e76c3e1b0938
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344748"
---
# <a name="how-to-animate-color-by-using-key-frames"></a>Cómo: Animar un color mediante fotogramas clave
En este ejemplo se <xref:System.Windows.Media.SolidColorBrush.Color%2A> muestra <xref:System.Windows.Media.SolidColorBrush> cómo animar la de a mediante fotogramas clave.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> siguiente se <xref:System.Windows.Media.SolidColorBrush.Color%2A> utiliza <xref:System.Windows.Media.SolidColorBrush>la clase para animar la propiedad de un archivo . Esta animación utiliza tres fotogramas clave de la siguiente manera:  
  
1. Durante los dos primeros segundos, <xref:System.Windows.Media.Animation.LinearColorKeyFrame> utiliza una instancia de la clase para cambiar gradualmente el color de verde a rojo. Los fotogramas <xref:System.Windows.Media.Animation.LinearColorKeyFrame> clave lineales como crean una transición lineal suave entre los valores.  
  
2. Durante el final del siguiente medio segundo, <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> utiliza una instancia de la clase para cambiar rápidamente el color de rojo a amarillo. Los fotogramas <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> clave discretos como crear cambios repentinos entre los valores, es decir, el cambio de color en esta parte de la animación se produce rápidamente y no es sutil.  
  
3. Durante los dos segundos finales, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplineColorKeyFrame> clase para cambiar el color de nuevo, esta vez de amarillo a verde. Los fotogramas <xref:System.Windows.Media.Animation.SplineColorKeyFrame> clave de spline como crean una <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> transición variable entre los valores según los valores de la propiedad. En este ejemplo, el cambio de color comienza despacio y se acelera exponencialmente hacia el final del segmento temporal.  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.SolidColorBrush.Color%2A>
- <xref:System.Windows.Media.SolidColorBrush>
- <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
- [Temas de procedimientos de fotogramas clave](key-frame-animation-how-to-topics.md)
