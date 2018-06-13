---
title: 'Cómo: Animar una propiedad usando un objeto AnimationClock'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], properties [WPF], with AnimationClocks
- AnimationClocks [WPF]
ms.assetid: e6542021-714c-4675-9567-04f1c7380834
ms.openlocfilehash: b8c64586d0dc5dc2e565fe4cb002e0f9cd4109af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558737"
---
# <a name="how-to-animate-a-property-by-using-an-animationclock"></a>Cómo: Animar una propiedad usando un objeto AnimationClock
Este ejemplo muestra cómo utilizar <xref:System.Windows.Media.Animation.Clock> objetos que se va a animar una propiedad.  
  
 Hay tres maneras de animar una propiedad de dependencia:  
  
-   Crear un <xref:System.Windows.Media.Animation.AnimationTimeline> y asociarlo a esa propiedad mediante el uso de un <xref:System.Windows.Media.Animation.Storyboard>.  
  
-   Usar el objeto <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método para aplicar una sola <xref:System.Windows.Media.Animation.AnimationTimeline> a una propiedad de destino.  
  
-   Crear un <xref:System.Windows.Media.Animation.AnimationClock> desde un <xref:System.Windows.Media.Animation.AnimationTimeline> y aplicarla a una propiedad.  
  
 <xref:System.Windows.Media.Animation.Storyboard> objetos y la <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método permiten animar propiedades sin directamente creación y distribución de relojes (para obtener ejemplos, vea [animar una propiedad mediante un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) y [animar una propiedad sin Con un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)); relojes se crean y se distribuyen automáticamente.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo crear un <xref:System.Windows.Media.Animation.AnimationClock> y aplicarlo a dos propiedades similares.  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 Para obtener un ejemplo que muestra cómo controlar interactivamente un <xref:System.Windows.Media.Animation.Clock> después de iniciarse, vea [controlar interactivamente un reloj](../../../../docs/framework/wpf/graphics-multimedia/how-to-interactively-control-a-clock.md).  
  
## <a name="see-also"></a>Vea también  
 [Animar una propiedad utilizando un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)  
 [Animar una propiedad sin utilizar un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)  
 [Información general sobre técnicas de animación de propiedades](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
