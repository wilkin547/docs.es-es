---
title: 'Cómo: Animar un objeto mediante fotogramas clave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: 0bc33b189fd856dbe8106c1db35bc18e27ea131e
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344703"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a>Cómo: Animar un objeto mediante fotogramas clave
En este ejemplo se muestra cómo animar un <xref:System.Windows.Controls.Page.Background%2A> objeto, <xref:System.Windows.Controls.Page> que en este ejemplo es la propiedad de un control, mediante marcos clave.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> siguiente se utiliza <xref:System.Windows.Controls.Page.Background%2A> la clase <xref:System.Windows.Controls.Page> para animar los cambios de color para la propiedad de un control. La animación de ejemplo cambia a un pincel de fondo diferente a intervalos regulares. Esta animación <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> utiliza la clase para crear tres fotogramas clave diferentes. La animación utiliza fotogramas clave de la siguiente manera:  
  
1. Al final del primer segundo, anima una <xref:System.Windows.Media.LinearGradientBrush> instancia de la clase. Esta sección del ejemplo aplica un degradado lineal al color de fondo para que el color pase de amarillo a naranja a rojo.  
  
2. Al final del segundo siguiente, anima una <xref:System.Windows.Media.RadialGradientBrush> instancia de la clase. Esta sección del ejemplo aplica un degradado radial al color de fondo para que el color pase de blanco a azul a negro.  
  
3. Al final del tercer segundo, anima una <xref:System.Windows.Media.DrawingBrush> instancia de la clase. Esta sección del ejemplo aplica un patrón de tablero de ajedrez al fondo.  
  
4. La animación comienza de nuevo y se repite indefinidamente.  
  
> [!NOTE]
> <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>es el único tipo de fotograma clave <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> que puede usar con la clase. Los fotogramas clave como <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> crear cambios repentinos en los valores, es decir, los cambios de color en este ejemplo se producen repentinamente.  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.Page.Background%2A>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- <xref:System.Windows.Media.DrawingBrush>
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
- [Temas de procedimientos de fotogramas clave](key-frame-animation-how-to-topics.md)
