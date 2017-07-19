---
title: "C&#243;mo: Asegurarse de que un GridSplitter es visible | Microsoft Docs"
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
  - "GridSplitter (control), garantizar la visibilidad de"
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Asegurarse de que un GridSplitter es visible
En este ejemplo se muestra cómo asegurarse de que los demás controles no ocultan un control <xref:System.Windows.Controls.GridSplitter> de un control <xref:System.Windows.Controls.Grid>.  
  
## Ejemplo  
 Las propiedades <xref:System.Windows.Controls.Panel.Children%2A> de un control <xref:System.Windows.Controls.Grid> se presentan en el orden en el que están definidas en el marcado o en el código.  Los controles <xref:System.Windows.Controls.GridSplitter> pueden quedar ocultos por otros controles si no se definen como los últimos elementos de la colección <xref:System.Windows.Controls.Panel.Children%2A> o si el campo <xref:System.Windows.Controls.Panel.ZIndexProperty> de estos otros controles se establece en un valor más alto.  
  
 Para evitar que los controles <xref:System.Windows.Controls.GridSplitter> queden ocultos, realice una de las acciones siguientes.  
  
-   Asegúrese de que los controles <xref:System.Windows.Controls.GridSplitter> son los últimos elementos <xref:System.Windows.Controls.Panel.Children%2A> agregados a <xref:System.Windows.Controls.Grid>.  En el ejemplo siguiente se muestra <xref:System.Windows.Controls.GridSplitter> como el último elemento de la colección <xref:System.Windows.Controls.Panel.Children%2A> de <xref:System.Windows.Controls.Grid>.  
  
 [!code-xml[GridSplitterSnips#GridSplitterLastChild](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
-   Establezca el campo <xref:System.Windows.Controls.Panel.ZIndexProperty> de <xref:System.Windows.Controls.GridSplitter> en un valor más alto que el del control que podría ocultarlo.  En el ejemplo siguiente se proporciona para el control <xref:System.Windows.Controls.GridSplitter> un valor de <xref:System.Windows.Controls.Panel.ZIndexProperty> más alto que el del control <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[GridSplitterSnips#GridSplitterZIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
-   Establezca márgenes en el control que podría ocultar el control <xref:System.Windows.Controls.GridSplitter>, de modo que <xref:System.Windows.Controls.GridSplitter> quede visible.  En el ejemplo siguiente se establecen márgenes en un control que podría superponerse al control <xref:System.Windows.Controls.GridSplitter> y ocultarlo.  
  
 [!code-xml[GridSplitterSnips#GridSplitterMargin](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## Vea también  
 <xref:System.Windows.Controls.GridSplitter>   
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)