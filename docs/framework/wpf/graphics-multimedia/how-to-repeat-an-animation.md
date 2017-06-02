---
title: "C&#243;mo: Repetir una animaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "animación, repetir"
  - "RepeatBehavior (propiedad de escalas de tiempo)"
  - "repetir la animación"
  - "RepeatBehavior (propiedad de escalas de tiempo)"
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Repetir una animaci&#243;n
En este ejemplo se muestra cómo utilizar la propiedad <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> de un objeto <xref:System.Windows.Media.Animation.Timeline> para controlar el comportamiento de repetición de una animación.  
  
## Ejemplo  
 La propiedad <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> de un objeto <xref:System.Windows.Media.Animation.Timeline> controla cuántas veces repite una animación su duración simple.  Utilizando <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, puede especificar que un objeto <xref:System.Windows.Media.Animation.Timeline> se repita un cierto número de veces \(un número de iteraciones\) o durante un período de tiempo especificado.  En cualquier caso, la animación pasa por tantas repeticiones de principio a fin como sea necesario necesita para rellenar el recuento o la duración solicitados.  
  
 De forma predeterminada, las escalas de tiempo tienen una cuenta de repeticiones de 1,0, lo que significa que se reproducen una vez y no se repiten.  Sin embargo, si establece la propiedad <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> de un objeto <xref:System.Windows.Media.Animation.Timeline> en <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, la escala de tiempo se repetirá indefinidamente.  
  
 En el ejemplo siguiente se muestra cómo utilizar la propiedad <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> para controlar el comportamiento de repetición de una animación.  El ejemplo anima la propiedad <xref:System.Windows.FrameworkElement.Width%2A> de cinco rectángulos, cada uno de los cuales utiliza un tipo diferente de comportamiento de repetición.  
  
 [!code-xml[timingbehaviors_snip#RepeatBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 Para obtener el ejemplo completo, vea [Animation Timing Behavior Sample](http://go.microsoft.com/fwlink/?LinkID=159970).  
  
## Vea también  
 [Acumular valores de animaciones durante la repetición de ciclos](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)   
 [Especificar si una escala de tiempo se invierte automáticamente](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-whether-a-timeline-automatically-reverses.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)   
 [Animation and Timing](http://msdn.microsoft.com/es-es/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Ejemplo Animation Timing Behavior](http://go.microsoft.com/fwlink/?LinkID=159970)