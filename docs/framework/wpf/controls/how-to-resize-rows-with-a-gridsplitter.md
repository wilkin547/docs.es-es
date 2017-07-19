---
title: "C&#243;mo: Cambiar el tama&#241;o de filas con un GridSplitter | Microsoft Docs"
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
  - "filas de cuadrícula, cambiar el tamaño"
  - "GridSplitter (control), cambiar el tamaño de las filas de la cuadrícula"
  - "cambiar el tamaño de las filas de la cuadrícula"
ms.assetid: 2413a9f2-1d81-46ed-95cb-95ec8233eea2
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Cambiar el tama&#241;o de filas con un GridSplitter
En este ejemplo se muestra cómo utilizar un <xref:System.Windows.Controls.GridSplitter> horizontal para redistribuir el espacio entre dos filas de un control <xref:System.Windows.Controls.Grid> sin cambiar las dimensiones de <xref:System.Windows.Controls.Grid>.  
  
## Ejemplo  
 **Cómo crear un GridSplitter que se superponga al borde de una fila**  
  
 Para especificar un control <xref:System.Windows.Controls.GridSplitter> que cambia el tamaño de las filas adyacentes en un control <xref:System.Windows.Controls.Grid>, establezca la [propiedad adjunta](GTMT) <xref:System.Windows.Controls.Grid.Row%2A> en una de las filas cuyo tamaño desea cambiar.  Si <xref:System.Windows.Controls.Grid> tiene más de una columna, establezca la propiedad adjunta <xref:System.Windows.Controls.Grid.ColumnSpan%2A> para especificar el número de columnas.  A continuación, establezca <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> en <xref:System.Windows.VerticalAlignment> o <xref:System.Windows.VerticalAlignment> \(la alineación que se establezca dependerá de cuáles sean las dos filas cuyo tamaño desea cambiar\).  Por último, establezca la propiedad <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> en <xref:System.Windows.HorizontalAlignment>.  
  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.GridSplitter> horizontal que cambia el tamaño de las filas adyacentes.  
  
 [!code-xml[GridSplitterRowColumn#GridSplitterRowOverlay](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterrowoverlay)]  
  
 Un <xref:System.Windows.Controls.GridSplitter> que no ocupe su propia fila podrá quedar oculto por otros controles de la cuadrícula \(<xref:System.Windows.Controls.Grid>\).  Para obtener más información sobre cómo evitar el problema, consulte [Asegurarse de que un GridSplitter es visible](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).  
  
 **Cómo crear un GridSplitter que ocupa una fila**  
  
 Para especificar un control <xref:System.Windows.Controls.GridSplitter> que ocupa una fila en un control <xref:System.Windows.Controls.Grid>, establezca la [propiedad adjunta](GTMT) <xref:System.Windows.Controls.Grid.Row%2A> en una de las filas cuyo tamaño desea cambiar.  Si <xref:System.Windows.Controls.Grid> tiene más de una columna, establezca la propiedad adjunta <xref:System.Windows.Controls.Grid.ColumnSpan%2A> en el número de columnas.  A continuación, establezca <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> en <xref:System.Windows.VerticalAlignment>, establezca la propiedad <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> en <xref:System.Windows.HorizontalAlignment> y establezca <xref:System.Windows.Controls.RowDefinition.Height%2A> de la fila que contiene el <xref:System.Windows.Controls.GridSplitter> en <xref:System.Windows.GridLength.Auto%2A>.  
  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.GridSplitter> horizontal que ocupa una fila y cambia el tamaño de las filas situadas a ambos lados de él.  
  
 [!code-xml[GridSplitterRowColumn#GridSplitterEntireRowPart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart1)]  
[!code-xml[GridSplitterRowColumn#GridSplitterEntireRowPart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart2)]  
  
## Vea también  
 <xref:System.Windows.Controls.GridSplitter>   
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)