---
title: "C&#243;mo: Buscar un reloj de forma sincr&#243;nica | Microsoft Docs"
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
  - "relojes, buscar de forma sincrónica"
  - "buscar relojes de forma sincrónica"
ms.assetid: e5b7529b-b7d0-40d2-9e1d-fa4b5e736e96
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# C&#243;mo: Buscar un reloj de forma sincr&#243;nica
Utilice el método <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> para buscar sincrónicamente en un reloj hasta un punto concreto.  En el siguiente ejemplo de código se muestran los métodos <xref:System.Windows.Media.Animation.ClockController.Seek%2A> y <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> de <xref:System.Windows.Media.Animation.ClockController>.  
  
 En este ejemplo se muestra cómo buscar en un <xref:System.Windows.Media.Animation.Clock>; para obtener un ejemplo que muestra cómo buscar en un guión gráfico, vea [Buscar guiones gráficos de forma sincrónica](../../../../docs/framework/wpf/graphics-multimedia/how-to-seek-a-storyboard-synchronously.md).  
  
## Ejemplo  
 [!code-csharp[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClockController_procedural_snip/CSharp/SeekAlignedToLastTickExample.cs#clockcontrollerseekexample)]
 [!code-vb[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClockController_procedural_snip/visualbasic/seekalignedtolasttickexample.vb#clockcontrollerseekexample)]