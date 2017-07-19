---
title: "C&#243;mo: Recibir una notificaci&#243;n cuando cambia el estado de un reloj | Microsoft Docs"
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
  - "relojes, notificación de cambios de estado"
  - "notificaciones, cambios de estado de reloj"
ms.assetid: ecb10fc9-d0c2-45c3-b0a1-7b11baa733da
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Recibir una notificaci&#243;n cuando cambia el estado de un reloj
Un evento <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> de reloj se produce cuando su propiedad <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> deja de ser válida, por ejemplo, cuando el reloj arranca o se para.  Se puede efectuar el registro para este evento utilizando directamente un objeto <xref:System.Windows.Media.Animation.Clock>, o bien mediante un objeto <xref:System.Windows.Media.Animation.Timeline>.  
  
 En el ejemplo siguiente, se utiliza un objeto <xref:System.Windows.Media.Animation.Storyboard> y dos objetos <xref:System.Windows.Media.Animation.DoubleAnimation> para animar el ancho de dos rectángulos.  El evento <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> se utiliza para realizar escuchas y detectar los cambios en el estado del reloj.  
  
## Ejemplo  
 [!code-xml[timingbehaviors_snip#_graphicsmm_StateExampleMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml#_graphicsmm_stateexamplemarkupwholepage)]  
  
 [!code-csharp[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml.cs#_graphicsmm_stateeventhandlers)]
 [!code-vb[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/stateexample.xaml.vb#_graphicsmm_stateeventhandlers)]  
  
 En la ilustración siguiente se muestran los distintos estados que adoptan las animaciones a medida que progresa la escala de tiempo primaria \(*Storyboard*\).  
  
 ![Estados de reloj para guión gráfico con dos animaciones](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-3timelines.png "graphicsmm\_3timelines")  
  
 En la tabla siguiente se muestra en qué momentos se activa el evento <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> de *Animation1*:  
  
||||||||  
|-|-|-|-|-|-|-|  
|Tiempo \(segundos\)|1|10|19|21|30|39|  
|Estado|Activo|Activo|Stopped|Activo|Activo|Stopped|  
  
 En la tabla siguiente se muestra en qué momentos se activa el evento <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> de *Animation2*:  
  
||||||||||  
|-|-|-|-|-|-|-|-|-|  
|Tiempo \(segundos\)|1|9|11|19|21|29|31|39|  
|Estado|Activo|Filling|Activo|Stopped|Activo|Filling|Activo|Stopped|  
  
 Observe que el evento <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> de *Animation1* se activa a los 10 segundos, aunque su estado sigue siendo <xref:System.Windows.Media.Animation.ClockState>.  Esto se debe a que su estado cambia a los 10 segundos, pero de <xref:System.Windows.Media.Animation.ClockState> a <xref:System.Windows.Media.Animation.ClockState> y, a continuación, vuelve a <xref:System.Windows.Media.Animation.ClockState> en el mismo paso.