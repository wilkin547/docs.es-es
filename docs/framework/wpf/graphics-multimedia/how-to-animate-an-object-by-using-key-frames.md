---
title: Procedimiento Animar un objeto mediante fotogramas clave
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: ffbe1845b634c8f94eb6a10dfa44fcf9903e0cd5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933909"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a>Procedimiento Animar un objeto mediante fotogramas clave
En este ejemplo se muestra cómo animar un objeto, que en este ejemplo <xref:System.Windows.Controls.Page.Background%2A> es la propiedad <xref:System.Windows.Controls.Page> de un control, mediante fotogramas clave.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> usa la clase para animar los <xref:System.Windows.Controls.Page.Background%2A> cambios de color <xref:System.Windows.Controls.Page> de la propiedad de un control. La animación de ejemplo cambia a un pincel de fondo diferente a intervalos regulares. Esta animación usa la <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> clase para crear tres fotogramas clave diferentes. La animación utiliza fotogramas clave de la siguiente manera:  
  
1. Al final del primer segundo, anima una instancia de la <xref:System.Windows.Media.LinearGradientBrush> clase. En esta sección del ejemplo se aplica un degradado lineal al color de fondo para que el color pase de amarillo a rojo.  
  
2. Al final del siguiente segundo, anima una instancia de la <xref:System.Windows.Media.RadialGradientBrush> clase. En esta sección del ejemplo se aplica un degradado radial al color de fondo para que el color pase de blanco a azul a negro.  
  
3. Al final del tercer segundo, anima una instancia de la <xref:System.Windows.Media.DrawingBrush> clase. En esta sección del ejemplo se aplica un patrón de tablero de ajedrez al fondo.  
  
4. La animación comienza de nuevo y se repite indefinidamente.  
  
> [!NOTE]
> <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>es el único tipo de fotograma clave que se puede utilizar con <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> la clase. Fotogramas <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> clave, como crear cambios súbitos en valores, es decir, los cambios de color de este ejemplo se producen repentinamente.  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
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
