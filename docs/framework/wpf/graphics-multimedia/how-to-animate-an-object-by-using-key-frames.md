---
title: Filtrar Animar un objeto mediante fotogramas clave
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: 0b2b517410c6cbc4f3deca13e5948c8de583fd3d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59177806"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a>Filtrar Animar un objeto mediante fotogramas clave
En este ejemplo se muestra cómo animar un objeto, que en este ejemplo es el <xref:System.Windows.Controls.Page.Background%2A> propiedad de un <xref:System.Windows.Controls.Page> control mediante fotogramas clave.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> clase se va a animar el color cambia para el <xref:System.Windows.Controls.Page.Background%2A> propiedad de un <xref:System.Windows.Controls.Page> control. La animación en el ejemplo se cambia a un pincel de fondo diferente a intervalos regulares. Esta animación usa el <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> clase para crear tres fotogramas clave diferentes. La animación utiliza fotogramas clave en la siguiente manera:  
  
1.  Al final del primer segundo, anima una instancia de la <xref:System.Windows.Media.LinearGradientBrush> clase. En esta sección del ejemplo aplica un degradado lineal al color de fondo para que el color pasa de amarillo a naranja a rojo.  
  
2.  Al final del segundo siguiente, anima una instancia de la <xref:System.Windows.Media.RadialGradientBrush> clase. En esta sección del ejemplo aplica un degradado radial al color de fondo para que el color pasa de negro a azul a negro.  
  
3.  Al final del tercer segundo, anima una instancia de la <xref:System.Windows.Media.DrawingBrush> clase. En esta sección del ejemplo se aplica un patrón de tablero a segundo plano.  
  
4.  La animación comienza de nuevo y se repite indefinidamente.  
  
> [!NOTE]
>  <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> es el único tipo de fotograma clave que puede usar con el <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> clase. Fotogramas clave como <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> crean cambios súbitos en valores, es decir, los cambios de color en este ejemplo se producen de repente.  
  
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
