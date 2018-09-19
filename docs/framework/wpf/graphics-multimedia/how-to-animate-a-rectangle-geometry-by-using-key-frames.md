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
ms.openlocfilehash: 9b4a620ea58026c3be1b09d01a595e965e4c2b45
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46002949"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a>Cómo: Animar la geometría de un rectángulo mediante fotogramas clave
En este ejemplo se muestra cómo animar la <xref:System.Windows.Media.RectangleGeometry.Rect%2A> propiedad de un <xref:System.Windows.Media.RectangleGeometry> mediante fotogramas clave.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> clase se va a animar el <xref:System.Windows.Media.RectangleGeometry.Rect%2A> propiedad de un <xref:System.Windows.Media.RectangleGeometry>. Esta animación utiliza tres fotogramas clave de la siguiente manera:  
  
1.  Durante los primeros dos segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.LinearRectKeyFrame> clase para animar un cambio gradual en la posición, ancho y alto de un rectángulo. Los fotogramas clave lineales como <xref:System.Windows.Media.Animation.LinearRectKeyFrame> crean una transición lineal suave entre valores.  
  
2.  Durante el fin de la siguiente medio segundo, utiliza una instancia de la <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> clase para reducir de repente el alto del rectángulo. Los fotogramas clave discretos como <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> crean cambios súbitos entre los valores, es decir, la reducción del alto se produce de forma rápida y brusca.  
  
3.  Durante los dos últimos segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplineRectKeyFrame> clase para cambiar el rectángulo a su tamaño y posición originales. Los fotogramas clave spline como <xref:System.Windows.Media.Animation.SplineRectKeyFrame> crean una transición variable entre los valores según los valores de la <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> propiedad. En este ejemplo, el cambio comienza despacio y se acelera exponencialmente hacia el final del segmento temporal.  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.RectangleGeometry>  
 <xref:System.Windows.Media.RectangleGeometry.Rect%2A>  
 <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>  
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Temas de procedimientos de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
