---
title: Procedimiento Animar una propiedad usando un objeto AnimationClock
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], properties [WPF], with AnimationClocks
- AnimationClocks [WPF]
ms.assetid: e6542021-714c-4675-9567-04f1c7380834
ms.openlocfilehash: d93f1eb352aef4f5e74512a8deeb0ec3fe7943c0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357188"
---
# <a name="how-to-animate-a-property-by-using-an-animationclock"></a>Procedimiento Animar una propiedad usando un objeto AnimationClock
En este ejemplo se muestra cómo usar <xref:System.Windows.Media.Animation.Clock> objetos que se va a animar una propiedad.  
  
 Hay tres maneras de animar una propiedad de dependencia:  
  
-   Crear un <xref:System.Windows.Media.Animation.AnimationTimeline> y asociarlo a esa propiedad mediante el uso de un <xref:System.Windows.Media.Animation.Storyboard>.  
  
-   Utilice el objeto <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método para aplicar una sola <xref:System.Windows.Media.Animation.AnimationTimeline> a una propiedad de destino.  
  
-   Crear un <xref:System.Windows.Media.Animation.AnimationClock> desde un <xref:System.Windows.Media.Animation.AnimationTimeline> y aplicarla a una propiedad.  
  
 <xref:System.Windows.Media.Animation.Storyboard> los objetos y el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método le permiten animar propiedades sin crear ni distribuir los relojes directamente (para obtener ejemplos, vea [animar una propiedad utilizando un guión gráfico](how-to-animate-a-property-by-using-a-storyboard.md) y [animar una propiedad sin Utilizar un guión gráfico](how-to-animate-a-property-without-using-a-storyboard.md)); los relojes se crean y distribuyen automáticamente.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo crear un <xref:System.Windows.Media.Animation.AnimationClock> y aplicarlo a dos propiedades similares.  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 Para obtener un ejemplo que muestra cómo controlar interactivamente un <xref:System.Windows.Media.Animation.Clock> después de iniciarse, vea [controlar interactivamente un reloj](how-to-interactively-control-a-clock.md).  
  
## <a name="see-also"></a>Vea también
- [Animar una propiedad utilizando un guión gráfico](how-to-animate-a-property-by-using-a-storyboard.md)
- [Animar una propiedad sin utilizar un guión gráfico](how-to-animate-a-property-without-using-a-storyboard.md)
- [Información general sobre técnicas de animación de propiedades](property-animation-techniques-overview.md)
