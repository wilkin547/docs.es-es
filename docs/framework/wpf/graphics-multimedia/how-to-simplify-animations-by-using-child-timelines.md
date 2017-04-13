---
title: "C&#243;mo: Simplificar animaciones utilizando objetos Timeline secundarios | Microsoft Docs"
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
  - "animación, simplificar mediante escalas de tiempo secundarias"
  - "escalas de tiempo secundarias"
  - "simplificar las animaciones mediante escalas de tiempo secundarias"
ms.assetid: 8335d770-d13d-42bd-8dfa-63f92c0327e2
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Simplificar animaciones utilizando objetos Timeline secundarios
En este ejemplo se muestra cómo simplificar las animaciones con objetos <xref:System.Windows.Media.Animation.ParallelTimeline> secundarios.  <xref:System.Windows.Media.Animation.Storyboard> es un tipo de <xref:System.Windows.Media.Animation.Timeline> que proporciona información de destino para las escalas de tiempo que contiene.  Utilice <xref:System.Windows.Media.Animation.Storyboard> para proporcionar información de destino para las escalas de tiempo, incluida la información de objetos y propiedades.  
  
 Para comenzar una animación, utilice uno o más objetos <xref:System.Windows.Media.Animation.ParallelTimeline> como elementos secundarios anidados de un objeto <xref:System.Windows.Media.Animation.Storyboard>.  Estos objetos <xref:System.Windows.Media.Animation.ParallelTimeline> pueden contener otras animaciones y, por consiguiente, pueden encapsular mejor las secuencias de control de tiempo en las animaciones complejas.  Por ejemplo, si va a animar un control <xref:System.Windows.Controls.TextBlock> y varias formas en el mismo objeto <xref:System.Windows.Media.Animation.Storyboard>, puede separar las animaciones correspondientes a <xref:System.Windows.Controls.TextBlock> y a las formas y colocar cada una de ellas en un objeto <xref:System.Windows.Media.Animation.ParallelTimeline> independiente.  Dado que <xref:System.Windows.Media.Animation.ParallelTimeline> tiene su propia propiedad <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> y que todos los elementos secundarios del objeto <xref:System.Windows.Media.Animation.ParallelTimeline> comienzan de manera relativa con respecto a <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>, es mejor encapsular el control de tiempo.  
  
 En el ejemplo siguiente se animan dos fragmentos de texto \(objetos <xref:System.Windows.Controls.TextBlock>\) desde el mismo objeto <xref:System.Windows.Media.Animation.Storyboard>.  <xref:System.Windows.Media.Animation.ParallelTimeline> encapsula las animaciones de uno de los objetos <xref:System.Windows.Controls.TextBlock>.  
  
 **Nota sobre rendimiento:** aunque puede anidar entre sí las escalas de tiempo de <xref:System.Windows.Media.Animation.Storyboard>, los objetos <xref:System.Windows.Media.Animation.ParallelTimeline> son más adecuados para la anidación, porque requieren menos sobrecarga.  \(La clase <xref:System.Windows.Media.Animation.Storyboard> hereda de la clase <xref:System.Windows.Media.Animation.ParallelTimeline>.\)  
  
## Ejemplo  
 [!code-xml[Timelines_snip#ParallelTimelineWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Timelines_snip/CS/ParallelTimelineExample.xaml#paralleltimelinewholepage)]  
  
## Vea también  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Especificar HandoffBehavior entre animaciones de guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-handoffbehavior-between-storyboard-animations.md)