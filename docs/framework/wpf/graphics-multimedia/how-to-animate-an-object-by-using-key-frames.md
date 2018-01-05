---
title: "Cómo: Animar un objeto mediante fotogramas clave"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5f513cda540b3337f1510ee0c46419a12023bcb6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a>Cómo: Animar un objeto mediante fotogramas clave
Este ejemplo muestra cómo animar un objeto, que en este ejemplo es el <xref:System.Windows.Controls.Page.Background%2A> propiedad de un <xref:System.Windows.Controls.Page> control, mediante el uso de fotogramas clave.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> clase animar color cambia para el <xref:System.Windows.Controls.Page.Background%2A> propiedad de un <xref:System.Windows.Controls.Page> control. La animación de ejemplo cambia a un pincel de fondo diferente a intervalos regulares. Esta animación usa la <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> clase para crear tres fotogramas clave diferentes. La animación usa fotogramas clave de la siguiente manera:  
  
1.  Al final del primer segundo, anima una instancia de la <xref:System.Windows.Media.LinearGradientBrush> clase. En esta sección del ejemplo se aplica un degradado lineal al color de fondo para que el color pasa de amarillo a naranja y a rojo.  
  
2.  Al final del segundo siguiente, anima una instancia de la <xref:System.Windows.Media.RadialGradientBrush> clase. En esta sección del ejemplo se aplica un degradado radial al color de fondo para que el color pasa de blanco a azul y a negro.  
  
3.  Al final del tercer segundo, anima una instancia de la <xref:System.Windows.Media.DrawingBrush> clase. Esta sección del ejemplo aplica un patrón de cuadros bicolores al fondo.  
  
4.  La animación comienza de nuevo y se repite indefinidamente.  
  
> [!NOTE]
>  <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>es el único tipo de fotograma clave que puede usar con la <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> clase. Fotogramas clave como <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> crean cambios repentinos en valores, es decir, los cambios de color en este ejemplo se producen de repente.  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>  
 <xref:System.Windows.Controls.Page.Background%2A>  
 <xref:System.Windows.Controls.Page>  
 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>  
 <xref:System.Windows.Media.LinearGradientBrush>  
 <xref:System.Windows.Media.RadialGradientBrush>  
 <xref:System.Windows.Media.DrawingBrush>  
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Temas de procedimientos de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
