---
title: "C&#243;mo: Utilizar las propiedades asociadas de Canvas para situar elementos secundarios | Microsoft Docs"
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
  - "propiedades asociadas [WPF Designer]"
  - "Canvas (control), propiedades asociadas"
ms.assetid: 48f1d25d-3820-4107-a4cc-d6c1e5664a44
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Utilizar las propiedades asociadas de Canvas para situar elementos secundarios
En este ejemplo se muestra cómo utilizar las [propiedades adjuntas](GTMT) de <xref:System.Windows.Controls.Canvas> para situar elementos secundarios.  
  
## Ejemplo  
 En el ejemplo siguiente se agregan cuatro elementos <xref:System.Windows.Controls.Button> como elementos secundarios de un objeto <xref:System.Windows.Controls.Canvas> primario.  Cada elemento secundario representa una propiedad adjunta distinta de <xref:System.Windows.Controls.Canvas>: <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A> y <xref:System.Windows.Controls.Canvas.Top%2A>.  Cada <xref:System.Windows.Controls.Button> se sitúa con respecto al objeto <xref:System.Windows.Controls.Canvas> primario y de acuerdo con su valor de propiedad asignado.  
  
 [!code-cpp[CanvasAttachedProperties#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/CanvasAttachedProperties/CPP/CanvasAttachedProps.cpp#1)]
 [!code-csharp[CanvasAttachedProperties#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasAttachedProperties/CSharp/CanvasAttachedProps.cs#1)]
 [!code-vb[CanvasAttachedProperties#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasAttachedProperties/VisualBasic/CanvasAttachedProps.vb#1)]  
  
## Vea también  
 <xref:System.Windows.Controls.Canvas>   
 <xref:System.Windows.Controls.Canvas.Bottom%2A>   
 <xref:System.Windows.Controls.Canvas.Left%2A>   
 <xref:System.Windows.Controls.Canvas.Right%2A>   
 <xref:System.Windows.Controls.Canvas.Top%2A>   
 <xref:System.Windows.Controls.Button>   
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/canvas-how-to-topics.md)   
 [Información general sobre propiedades asociadas](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)