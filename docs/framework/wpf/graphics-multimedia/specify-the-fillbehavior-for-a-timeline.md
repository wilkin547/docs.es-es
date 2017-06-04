---
title: "C&#243;mo: Especificar el comportamiento de relleno de una escala de tiempo que ha llegado al final de su per&#237;odo de actividad | Microsoft Docs"
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
  - "FillBehavior (propiedad) para escalas de tiempo inactivas"
  - "Escalas de tiempo, FillBehavior (propiedad)"
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Especificar el comportamiento de relleno de una escala de tiempo que ha llegado al final de su per&#237;odo de actividad
En este ejemplo se muestra cómo especificar <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> para el elemento <xref:System.Windows.Media.Animation.Timeline> inactivo de una propiedad animada.  
  
## Ejemplo  
 La propiedad <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> de <xref:System.Windows.Media.Animation.Timeline> determina lo que le ocurre al valor de una propiedad animada cuando no se está animando, es decir, cuando el elemento <xref:System.Windows.Media.Animation.Timeline> está inactivo pero su elemento <xref:System.Windows.Media.Animation.Timeline> primario está dentro de su período de actividad o de espera.  Por ejemplo, ¿una propiedad animada permanece en su valor final después de que la animación finaliza o retoma el valor que tenía antes de que la animación se iniciara?  
  
 En el ejemplo siguiente se usa <xref:System.Windows.Media.Animation.DoubleAnimation> para animar la propiedad <xref:System.Windows.FrameworkElement.Width%2A> de dos rectángulos.  Cada rectángulo usa un objeto <xref:System.Windows.Media.Animation.Timeline> diferente.  
  
 Un objeto <xref:System.Windows.Media.Animation.Timeline> tiene una propiedad <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> que está establecida en <xref:System.Windows.Media.Animation.FillBehavior>, lo que hace que el ancho del rectángulo recupere su valor no animado cuando <xref:System.Windows.Media.Animation.Timeline> finaliza.  El otro objeto <xref:System.Windows.Media.Animation.Timeline> tiene la propiedad <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> establecida en <xref:System.Windows.Media.Animation.FillBehavior>, lo que hace que el ancho permanezca en su valor final cuando <xref:System.Windows.Media.Animation.Timeline> finaliza.  
  
 [!code-xml[timingbehaviors_snip#FillBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 Para tener el ejemplo completo, vea [Animation Example Gallery](http://go.microsoft.com/fwlink/?LinkID=159969).  
  
## Vea también  
 <xref:System.Windows.Media.Animation.DoubleAnimation>   
 <xref:System.Windows.FrameworkElement.Width%2A>   
 <xref:System.Windows.Media.Animation.Timeline>   
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>   
 <xref:System.Windows.Media.Animation.FillBehavior>   
 <xref:System.Windows.Media.Animation.FillBehavior>   
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Animation and Timing](http://msdn.microsoft.com/es-es/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)