---
title: "C&#243;mo: Usar la propiedad BetweenShowDelay | Microsoft Docs"
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
  - "BetweenShowDelay (propiedad de tiempo)"
  - "ToolTip (control), BetweenShowDelay (propiedad de tiempo)"
ms.assetid: 984ea76d-f2a2-4326-a02e-f97ec3d036d6
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Usar la propiedad BetweenShowDelay
En este ejemplo se muestra cómo usar la propiedad de tiempo <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> para que la información sobre herramientas aparezca rápidamente, con poco o ningún retraso, cuando un usuario mueve el puntero del mouse directamente de una información sobre herramientas a otra.  
  
## Ejemplo  
 En el ejemplo siguiente, la propiedad <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> está establecida en un segundo \(1000 milisegundos\) y <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> está establecida en dos segundos \(2000 milisegundos\) para las informaciones sobre herramientas de los dos controles <xref:System.Windows.Shapes.Ellipse>.  Si muestra la información sobre herramientas de una de las elipses y, a continuación, en dos segundos, mueve el puntero del mouse a otra elipse y se detiene en ella, la información sobre herramientas de la segunda elipse se muestra inmediatamente.  
  
 En cualquiera de los casos siguientes, se aplica <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> y, por tanto, la información sobre herramientas de la segunda elipse espera un segundo antes de aparecer:  
  
-   Si el tiempo que se tarda en ir al segundo botón es superior a dos segundos.  
  
-   Si la información sobre herramientas no está visible al principio del intervalo de tiempo de la primera elipse.  
  
 [!code-xml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## Vea también  
 <xref:System.Windows.Controls.ToolTip>   
 <xref:System.Windows.Controls.ToolTipService>   
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)   
 [Información general de información sobre herramientas](../../../../docs/framework/wpf/controls/tooltip-overview.md)