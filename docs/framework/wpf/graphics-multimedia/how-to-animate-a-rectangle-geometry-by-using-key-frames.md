---
title: "Cómo: Animar la geometría de un rectángulo mediante fotogramas clave"
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
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5f110bcea76a61d46932c9e1aacf27f6f3255a91
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a>Cómo: Animar la geometría de un rectángulo mediante fotogramas clave
Este ejemplo muestra cómo animar la <xref:System.Windows.Media.RectangleGeometry.Rect%2A> propiedad de un <xref:System.Windows.Media.RectangleGeometry> mediante el uso de fotogramas clave.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> clase para animar la <xref:System.Windows.Media.RectangleGeometry.Rect%2A> propiedad de un <xref:System.Windows.Media.RectangleGeometry>. Esta animación utiliza tres fotogramas clave de la siguiente manera:  
  
1.  Durante los primeros dos segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.LinearRectKeyFrame> clase para animar un cambio gradual en la posición, el ancho y el alto de un rectángulo. Al igual que los fotogramas clave lineales <xref:System.Windows.Media.Animation.LinearRectKeyFrame> crear una transición lineal suave entre valores.  
  
2.  Durante el final de la siguiente medio segundo, utiliza una instancia de la <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> clase repentinamente reducir el alto del rectángulo. Los fotogramas clave discretos como <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> crear cambios bruscos entre valores, es decir, la disminución de alto se produce con rapidez y no es sutil.  
  
3.  Durante los últimos dos segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplineRectKeyFrame> clase para cambiar el rectángulo a su tamaño y posición original. Al igual que los fotogramas clave spline <xref:System.Windows.Media.Animation.SplineRectKeyFrame> crear una transición variable entre los valores según los valores de la <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> propiedad. En este ejemplo, el cambio comienza despacio y se acelera exponencialmente hacia el final del segmento temporal.  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.RectangleGeometry>  
 <xref:System.Windows.Media.RectangleGeometry.Rect%2A>  
 <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>  
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Temas de procedimientos de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
