---
title: "C&#243;mo: Especificar HandoffBehavior entre animaciones de gui&#243;n gr&#225;fico | Microsoft Docs"
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
  - "animación, comportamiento de entrega entre"
  - "Guiones gráficos, comportamiento de entrega entre animaciones"
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Especificar HandoffBehavior entre animaciones de gui&#243;n gr&#225;fico
En este ejemplo se muestra cómo especificar el comportamiento de entrega entre animaciones de guión gráfico.  La propiedad <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> de <xref:System.Windows.Media.Animation.BeginStoryboard> especifica cómo interactúan las nuevas animaciones con las existentes que ya se aplicaron a una propiedad.  
  
## Ejemplo  
 En el ejemplo siguiente se crean dos botones que aumentan de tamaño cuando el cursor del mouse se mueve por encima de ellos y disminuyen de tamaño cuando el cursor se aleja.  Si pasa el mouse por encima de un botón y lo quita rápidamente, la segunda animación se aplicará antes de que la primera haya finalizado.  Cuando dos animaciones se superponen de esta manera es cuando se aprecia la diferencia entre los valores <xref:System.Windows.Media.Animation.HandoffBehavior> y <xref:System.Windows.Media.Animation.HandoffBehavior> de <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>.  El valor <xref:System.Windows.Media.Animation.HandoffBehavior> combina las animaciones superpuestas y crea una transición más suave entre ambas, mientras que el valor <xref:System.Windows.Media.Animation.HandoffBehavior> hace que la nueva animación reemplace inmediatamente la anterior.  
  
 [!code-xml[timingbehaviors_snip#HandoffBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## Vea también  
 <xref:System.Windows.Media.Animation.BeginStoryboard>   
 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>   
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Animation and Timing](http://msdn.microsoft.com/es-es/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)