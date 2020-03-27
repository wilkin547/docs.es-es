---
title: 'Cómo: Animar el grosor de un borde mediante fotogramas clave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
ms.openlocfilehash: 884b62e88c347449ae39caa9c028d09db39b9f4b
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344695"
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a>Cómo: Animar el grosor de un borde mediante fotogramas clave
En este ejemplo se <xref:System.Windows.Controls.Control.BorderThickness%2A> muestra <xref:System.Windows.Controls.Border>cómo animar la propiedad de un archivo .  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> siguiente se <xref:System.Windows.Controls.Control.BorderThickness%2A> utiliza <xref:System.Windows.Controls.Border>la clase para animar la propiedad de un archivo . Esta animación utiliza tres fotogramas clave de la siguiente manera:  
  
1. Durante el primer medio segundo, <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> utiliza una instancia de la clase para aumentar gradualmente el grosor del borde. El ejemplo <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> se utiliza para crear un aumento lineal suave entre los valores.  
  
2. Al final del siguiente medio segundo, utiliza <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> una instancia de la clase para aumentar repentinamente el grosor del borde. Los fotogramas clave discretos como los derivados de <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> crear saltos repentinos entre los valores, es decir, el movimiento de la animación es desigual.  
  
3. Durante los dos segundos finales, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> clase para disminuir el grosor del borde. Los fotogramas clave de <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> spline como los derivados crean <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> una transición variable entre los valores según los valores de la propiedad. En este fotograma clave, la animación se inicia lentamente y se va acelerando de forma exponencial hacia el final del segmento temporal.  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
- [Temas de procedimientos de fotogramas clave](key-frame-animation-how-to-topics.md)
- [Animar el valor del grosor de un borde](../controls/how-to-animate-a-borderthickness-value.md)
