---
title: "C&#243;mo: Enumerar el contenido de un dibujo de un objeto Visual | Microsoft Docs"
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
  - "enumerar el contenido de un elemento visual [WPF]"
  - "recuperar el valor DrawingGroup de un elemento visual [WPF]"
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
caps.latest.revision: 3
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 3
---
# C&#243;mo: Enumerar el contenido de un dibujo de un objeto Visual
El objeto <xref:System.Windows.Media.Drawing> proporciona un modelo de objetos para enumerar el contenido de un objeto <xref:System.Windows.Media.Visual>.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza el método <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> para recuperar el valor de <xref:System.Windows.Media.DrawingGroup> de un objeto <xref:System.Windows.Media.Visual> y enumerarlo.  
  
> [!NOTE]
>  Al enumerar el contenido del elemento visual, se recuperan objetos <xref:System.Windows.Media.Drawing>, no la representación subyacente de los datos de representación como una lista de instrucciones de gráficos vectoriales.  Para obtener más información, vea [Información general sobre la representación de gráficos en WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## Vea también  
 <xref:System.Windows.Media.Drawing>   
 <xref:System.Windows.Media.DrawingGroup>   
 <xref:System.Windows.Media.VisualTreeHelper>   
 [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [Información general sobre la representación de gráficos en WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)