---
title: "C&#243;mo: Aplicar un objeto GuidelineSet a un dibujo | Microsoft Docs"
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
  - "gráficos [WPF], GuidelineSet (propiedad)"
  - "GuidelineSet (propiedad), aplicar a dibujos"
ms.assetid: 45f3e0b4-8820-45a7-b865-b8ea5b17b0c8
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Aplicar un objeto GuidelineSet a un dibujo
En este ejemplo, se muestra cómo aplicar una propiedad <xref:System.Windows.Media.GuidelineSet> a un objeto <xref:System.Windows.Media.DrawingGroup>.  
  
 La clase <xref:System.Windows.Media.DrawingGroup> es el único tipo de <xref:System.Windows.Media.Drawing> que tiene una propiedad <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>.  Para aplicar <xref:System.Windows.Media.GuidelineSet> a otro tipo de <xref:System.Windows.Media.Drawing>, deberá agregarla a un objeto <xref:System.Windows.Media.DrawingGroup> y, a continuación, aplicar <xref:System.Windows.Media.GuidelineSet> a <xref:System.Windows.Media.DrawingGroup>.  
  
## Ejemplo  
 En el ejemplo siguiente se crean dos objetos <xref:System.Windows.Media.DrawingGroup> que son casi idénticos; la única diferencia es que el segundo objeto <xref:System.Windows.Media.DrawingGroup> tiene la propiedad <xref:System.Windows.Media.GuidelineSet> y el primero, no.  
  
 En la siguiente ilustración se muestra el resultado del ejemplo.  Dado que la diferencia de representación entre los dos objetos <xref:System.Windows.Media.DrawingGroup> es tan sutil, se han ampliado las partes correspondientes de los dibujos.  
  
 ![DrawingGroup con y sin GuidelineSet](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm\_drawinggroup\_guidelineset")  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupGuidelineSetExample.cs#graphicsmmdrawinggroupguidelinesetexamplewholepage)]
 [!code-xml[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupGuidelineSetExample.xaml#graphicsmmdrawinggroupguidelinesetexamplewholepage)]  
  
## Vea también  
 <xref:System.Windows.Media.DrawingGroup>   
 <xref:System.Windows.Media.GuidelineSet>   
 [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)