---
title: 'Cómo: Animar la geometría de un rectángulo mediante fotogramas clave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
ms.openlocfilehash: bcc9e7f198b8a20ffe13daf6508fb8a735937652
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344680"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a>Cómo: Animar la geometría de un rectángulo mediante fotogramas clave
En este ejemplo se <xref:System.Windows.Media.RectangleGeometry.Rect%2A> muestra <xref:System.Windows.Media.RectangleGeometry> cómo animar la propiedad de a mediante fotogramas clave.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> siguiente se <xref:System.Windows.Media.RectangleGeometry.Rect%2A> utiliza <xref:System.Windows.Media.RectangleGeometry>la clase para animar la propiedad de un archivo . Esta animación utiliza tres fotogramas clave de la siguiente manera:  
  
1. Durante los dos primeros segundos, <xref:System.Windows.Media.Animation.LinearRectKeyFrame> utiliza una instancia de la clase para animar un cambio gradual en la posición, anchura y altura de un rectángulo. Los fotogramas <xref:System.Windows.Media.Animation.LinearRectKeyFrame> clave lineales como crean una transición lineal suave entre los valores.  
  
2. Durante el final del siguiente medio segundo, <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> utiliza una instancia de la clase para disminuir repentinamente la altura del rectángulo. Los fotogramas <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> clave discretos como crear cambios repentinos entre los valores, es decir, la disminución de la altura se produce rápidamente y no es sutil.  
  
3. Durante los dos segundos finales, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplineRectKeyFrame> clase para cambiar el rectángulo a su tamaño y posición originales. Los fotogramas <xref:System.Windows.Media.Animation.SplineRectKeyFrame> clave de spline como crean una <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> transición variable entre los valores según los valores de la propiedad. En este ejemplo, el cambio comienza despacio y se acelera exponencialmente hacia el final del segmento temporal.  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.RectangleGeometry>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
- [Temas de procedimientos de fotogramas clave](key-frame-animation-how-to-topics.md)
