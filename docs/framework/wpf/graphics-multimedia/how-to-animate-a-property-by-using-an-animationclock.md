---
title: "C&#243;mo: Animar una propiedad usando un objeto AnimationClock | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "animación, propiedades, con AnimationClocks"
  - "AnimationClocks"
ms.assetid: e6542021-714c-4675-9567-04f1c7380834
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Animar una propiedad usando un objeto AnimationClock
En este ejemplo se muestra cómo utilizar objetos <xref:System.Windows.Media.Animation.Clock> para animar una propiedad.  
  
 Hay tres maneras de animar una [propiedad de dependencia](GTMT):  
  
-   Crear un objeto <xref:System.Windows.Media.Animation.AnimationTimeline> y asociarlo a esa propiedad mediante un objeto <xref:System.Windows.Media.Animation.Storyboard>.  
  
-   Utilizar el método <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> del objeto para aplicar un único objeto <xref:System.Windows.Media.Animation.AnimationTimeline> a una propiedad de destino.  
  
-   Crear un objeto <xref:System.Windows.Media.Animation.AnimationClock> a partir de un objeto <xref:System.Windows.Media.Animation.AnimationTimeline> y aplicárselo a una propiedad.  
  
 Los objetos <xref:System.Windows.Media.Animation.Storyboard> y el método <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> permiten animar propiedades sin crear ni distribuir directamente relojes \(para obtener ejemplos, vea [Animar una propiedad utilizando un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) y [Animar una propiedad sin utilizar un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)\); los relojes se crean y distribuyen automáticamente.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo crear un objeto <xref:System.Windows.Media.Animation.AnimationClock> y aplicarlo a dos propiedades similares.  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 Para obtener un ejemplo que muestra cómo controlar interactivamente un objeto <xref:System.Windows.Media.Animation.Clock> después de iniciarse, vea [Controlar interactivamente un reloj](../../../../docs/framework/wpf/graphics-multimedia/how-to-interactively-control-a-clock.md).  
  
## Vea también  
 [Animar una propiedad utilizando un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)   
 [Animar una propiedad sin utilizar un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)   
 [Información general sobre técnicas de animación de propiedades](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)