---
title: "C&#243;mo crear y utilizar un control Canvas | Microsoft Docs"
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
  - "Canvas (control), crear"
  - "Canvas (control), utilizar"
  - "controles, Canvas"
ms.assetid: 420b9487-9a15-477c-9489-a22a4dec7779
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo crear y utilizar un control Canvas
En este ejemplo se muestra cómo crear y utilizar una instancia de <xref:System.Windows.Controls.Canvas>.  
  
## Ejemplo  
 En el ejemplo siguiente se colocan explícitamente dos elementos <xref:System.Windows.Controls.TextBlock> mediante los métodos <xref:System.Windows.Controls.Canvas.SetTop%2A> y <xref:System.Windows.Controls.Canvas.SetLeft%2A> de <xref:System.Windows.Controls.Canvas>.  En el ejemplo también se asigna el color `LightSteelBlue` de fondo \(<xref:System.Windows.Controls.Control.Background%2A>\) a <xref:System.Windows.Controls.Canvas>.  
  
> [!NOTE]
>  Cuando utilice [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para colocar elementos <xref:System.Windows.Controls.TextBlock>, utilice las propiedades <xref:System.Windows.Controls.Canvas.Top%2A> y <xref:System.Windows.Controls.Canvas.Left%2A>.  
  
 [!code-csharp[CanvasCode#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasCode/CSharp/Canvas_Code.cs#1)]
 [!code-vb[CanvasCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasCode/VisualBasic/canvas_vb.vb#1)]  
  
## Vea también  
 <xref:System.Windows.Controls.Canvas>   
 <xref:System.Windows.Controls.TextBlock>   
 <xref:System.Windows.Controls.Canvas.SetTop%2A>   
 <xref:System.Windows.Controls.Canvas.SetLeft%2A>   
 <xref:System.Windows.Controls.Canvas.Top%2A>   
 <xref:System.Windows.Controls.Canvas.Left%2A>   
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/canvas-how-to-topics.md)