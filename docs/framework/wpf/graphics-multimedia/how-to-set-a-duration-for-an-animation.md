---
title: "C&#243;mo: Definir una duraci&#243;n para una animaci&#243;n | Microsoft Docs"
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
  - "animación, duración"
  - "duración de las animaciones"
  - "Escalas de tiempo, description"
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Definir una duraci&#243;n para una animaci&#243;n
Un objeto <xref:System.Windows.Media.Animation.Timeline> representa un segmento de tiempo cuya longitud viene determinada por el objeto <xref:System.Windows.Duration> de la escala de tiempo.  Cuando una escala de tiempo \(<xref:System.Windows.Media.Animation.Timeline>\) llega al fin de su duración, su reproducción se detiene.  Si <xref:System.Windows.Media.Animation.Timeline> tiene escalas de tiempo secundarias, también se detiene su reproducción.  En el caso de una animación, <xref:System.Windows.Duration> especifica cuánto tiempo tarda la animación en efectuar la transición desde su valor inicial hasta su valor final.  
  
 Puede especificar <xref:System.Windows.Duration> con un tiempo concreto y finito o utilizar los valores especiales de <xref:System.Windows.Duration.Automatic%2A> o <xref:System.Windows.Duration.Forever%2A>.  La duración de una animación siempre debe ser un valor de tiempo, porque una animación siempre debe tener una duración finita y definida; de lo contrario, no sabría cómo realizar la transición entre sus valores de destino.  Las escalas de tiempo contenedoras \(objetos <xref:System.Windows.Media.Animation.TimelineGroup>\), como <xref:System.Windows.Media.Animation.Storyboard> y <xref:System.Windows.Media.Animation.ParallelTimeline>, tienen una duración predeterminada de <xref:System.Windows.Duration.Automatic%2A>, lo que quiere decir que finalizan automáticamente cuando se detiene la reproducción de la última escala de tiempo secundaria.  
  
 En el ejemplo siguiente, se animan el ancho, alto y color de relleno de <xref:System.Windows.Shapes.Rectangle>.  Las duraciones se establecen mediante escalas de tiempo de animación y contenedoras; esto da lugar a que los efectos de animación incluyan el control de la velocidad percibida de una animación y a que invaliden la duración de las escalas de tiempo secundarias con la duración de una escala de tiempo contenedora.  
  
## Ejemplo  
 [!code-xml[timingbehaviors_snip#DurationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## Vea también  
 <xref:System.Windows.Duration>   
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)