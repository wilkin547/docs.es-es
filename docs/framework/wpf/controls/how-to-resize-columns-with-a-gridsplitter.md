---
title: "C&#243;mo: Cambiar el tama&#241;o de columnas con un GridSplitter | Microsoft Docs"
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
  - "columnas de cuadrícula, cambiar el tamaño"
  - "GridSplitter (control), cambiar el tamaño de las columnas de la cuadrícula"
  - "cambiar el tamaño de las columnas de la cuadrícula"
ms.assetid: 47b20fe6-7adc-4aa6-9693-b4e184eef74b
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Cambiar el tama&#241;o de columnas con un GridSplitter
En este ejemplo se muestra cómo crear un <xref:System.Windows.Controls.GridSplitter> vertical para redistribuir el espacio entre dos columnas en un control <xref:System.Windows.Controls.Grid> sin cambiar las dimensiones de <xref:System.Windows.Controls.Grid>.  
  
## Ejemplo  
 **Cómo crear un GridSplitter que se superponga al borde de una columna**  
  
 Para especificar un control <xref:System.Windows.Controls.GridSplitter> que cambia el tamaño de las columnas adyacentes en un control <xref:System.Windows.Controls.Grid>, establezca la [propiedad adjunta](GTMT) <xref:System.Windows.Controls.Grid.Column%2A> en una de las columnas cuyo tamaño desea cambiar.  Si <xref:System.Windows.Controls.Grid> tiene más de una fila, establezca la propiedad adjunta <xref:System.Windows.Controls.Grid.RowSpan%2A> en el número de filas.  A continuación, establezca la propiedad <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> en <xref:System.Windows.HorizontalAlignment> o <xref:System.Windows.HorizontalAlignment> \(la alineación que se establezca dependerá de cuáles sean las dos columnas cuyo tamaño desea cambiar\).  Por último, establezca la propiedad <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> en <xref:System.Windows.VerticalAlignment>.  
  
 [!code-xml[GridSplitterRowColumn#GridSplitterColumnOverlay](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplittercolumnoverlay)]  
  
 Un <xref:System.Windows.Controls.GridSplitter> que no tenga su propia columna puede quedar oculto tras otros controles de <xref:System.Windows.Controls.Grid>.  Para obtener más información sobre cómo evitar el problema, consulte [Asegurarse de que un GridSplitter es visible](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).  
  
 **Cómo crear un GridSplitter que ocupa una columna**  
  
 Para especificar un control <xref:System.Windows.Controls.GridSplitter> que ocupa una columna de un control <xref:System.Windows.Controls.Grid>, establezca la [propiedad adjunta](GTMT) <xref:System.Windows.Controls.Grid.Column%2A> en una de las columnas cuyo tamaño desea cambiar.  Si la cuadrícula tiene más de una fila, establezca la propiedad adjunta <xref:System.Windows.Controls.Grid.RowSpan%2A> en el número de filas.  A continuación, establezca <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> en <xref:System.Windows.HorizontalAlignment>, establezca la propiedad <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> en <xref:System.Windows.VerticalAlignment> y establezca <xref:System.Windows.Controls.ColumnDefinition.Width%2A> de la columna que contiene el <xref:System.Windows.Controls.GridSplitter> en <xref:System.Windows.GridLength.Auto%2A>.  
  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.GridSplitter> vertical que ocupa una columna y cambia el tamaño de las columnas situadas a ambos lados de él.  
  
 [!code-xml[GridSplitterRowColumn#GridSplitterEntireColumnPart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart1)]  
[!code-xml[GridSplitterRowColumn#GridSplitterEntireColumnPart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart2)]  
  
## Vea también  
 <xref:System.Windows.Controls.GridSplitter>   
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)