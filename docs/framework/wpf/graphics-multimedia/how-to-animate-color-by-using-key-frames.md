---
title: "Cómo: Animar un color mediante fotogramas clave"
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
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d117d57e5cc761aa2f31fd6531bff8d96ea30dc3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-color-by-using-key-frames"></a>Cómo: Animar un color mediante fotogramas clave
Este ejemplo muestra cómo animar la <xref:System.Windows.Media.SolidColorBrush.Color%2A> de un <xref:System.Windows.Media.SolidColorBrush> mediante el uso de fotogramas clave.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> clase para animar la <xref:System.Windows.Media.SolidColorBrush.Color%2A> propiedad de un <xref:System.Windows.Media.SolidColorBrush>. Esta animación utiliza tres fotogramas clave de la siguiente manera:  
  
1.  Durante los primeros dos segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.LinearColorKeyFrame> clase cambian gradualmente el color de verde a rojo. Al igual que los fotogramas clave lineales <xref:System.Windows.Media.Animation.LinearColorKeyFrame> crear una transición lineal suave entre valores.  
  
2.  Durante el final de la siguiente medio segundo, utiliza una instancia de la <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> clase para cambiar rápidamente el color de rojo a amarillo. Los fotogramas clave discretos como <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> crear cambios bruscos entre valores, es decir, el cambio de color en esta parte de la animación se produce con rapidez y no es sutil.  
  
3.  Durante los últimos dos segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplineColorKeyFrame> clase para cambiar el color de nuevo, esta vez de amarillo a verde. Al igual que los fotogramas clave spline <xref:System.Windows.Media.Animation.SplineColorKeyFrame> crear una transición variable entre los valores según los valores de la <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> propiedad. En este ejemplo, el cambio de color comienza despacio y se acelera exponencialmente hacia el final del segmento temporal.  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.SolidColorBrush.Color%2A>  
 <xref:System.Windows.Media.SolidColorBrush>  
 <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>  
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Temas de procedimientos de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
