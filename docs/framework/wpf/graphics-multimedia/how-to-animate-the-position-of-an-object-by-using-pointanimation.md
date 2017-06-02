---
title: "C&#243;mo: Animar la posici&#243;n de un objeto mediante PointAnimation | Microsoft Docs"
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
  - "animación, PointAnimation"
  - "clases, PointAnimation"
  - "gráficos [WPF], animación"
  - "PointAnimation (clase)"
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Animar la posici&#243;n de un objeto mediante PointAnimation
En este ejemplo se muestra cómo utilizar la clase <xref:System.Windows.Media.Animation.PointAnimation> para animar un objeto a lo largo de una trayectoria \(<xref:System.Windows.Shapes.Path>\).  
  
## Ejemplo  
 En el ejemplo siguiente se mueve una elipse a lo largo de <xref:System.Windows.Shapes.Path>, de un punto a otro de la pantalla.  En el ejemplo, se anima la posición de <xref:System.Windows.Media.EllipseGeometry>; para ello, se anima la propiedad <xref:System.Windows.Media.EllipseGeometry.Center%2A> mediante <xref:System.Windows.Media.Animation.PointAnimation>.  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## Vea también  
 <xref:System.Windows.Media.Animation.PointAnimation>   
 <xref:System.Windows.Shapes.Path>   
 <xref:System.Windows.Media.EllipseGeometry>   
 <xref:System.Windows.Media.EllipseGeometry.Center%2A>   
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Gráficos y multimedia](../../../../docs/framework/wpf/graphics-multimedia/index.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/graphics-how-to-topics.md)   
 [Animation and Timing](http://msdn.microsoft.com/es-es/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)