---
title: "C&#243;mo: Utilizar plantillas para aplicar un estilo a un control ListView que utiliza un modo GridView | Microsoft Docs"
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
  - "ListView (controles), aplicar estilos"
ms.assetid: 94bf964b-96c8-4bdf-a0c3-f5271b7cb565
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Utilizar plantillas para aplicar un estilo a un control ListView que utiliza un modo GridView
En este ejemplo se muestra cómo usar los objetos <xref:System.Windows.DataTemplate> y <xref:System.Windows.Style> para especificar la apariencia de un control <xref:System.Windows.Controls.ListView> que usa un modo de vista <xref:System.Windows.Controls.GridView>.  
  
## Ejemplo  
 En los ejemplos siguientes se muestran objetos <xref:System.Windows.Style> y <xref:System.Windows.DataTemplate> que personalizan la apariencia de un encabezado de columna para <xref:System.Windows.Controls.GridViewColumn>.  
  
 [!code-xml[ListViewTemplate#GridViewHeaderStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheaderstyle)]  
  
 [!code-xml[ListViewTemplate#GridViewHeaderTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheadertemplate)]  
  
 En el ejemplo siguiente se muestra cómo usar estos objetos <xref:System.Windows.Style> y <xref:System.Windows.DataTemplate> para establecer las propiedades <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> y <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> de <xref:System.Windows.Controls.GridViewColumn>.  La propiedad <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> define el contenido de las celdas de columna.  
  
 [!code-xml[ListViewTemplate#GridViewColumnTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcolumntemplate)]  
  
 <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> y <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> son sólo dos de varias propiedades que puede usar para personalizar la apariencia del encabezado de columna para un control <xref:System.Windows.Controls.GridView>.  Para obtener más información, vea [Información general sobre plantillas y estilos de encabezado de columna en modo GridView](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md).  
  
 En el ejemplo siguiente se muestra cómo definir una <xref:System.Windows.DataTemplate> que personaliza la apariencia de las celdas de <xref:System.Windows.Controls.GridViewColumn>.  
  
 [!code-xml[ListViewTemplate#GridViewCellTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 En el ejemplo siguiente se muestra cómo usar <xref:System.Windows.DataTemplate> para definir el contenido de una celda de <xref:System.Windows.Controls.GridViewColumn>.  Esta plantilla se usa en lugar de la propiedad <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> que se muestra en el ejemplo de <xref:System.Windows.Controls.GridViewColumn> anterior.  
  
 [!code-xml[ListViewTemplate#CellTemplateProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
## Vea también  
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [Información general sobre GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [Información general sobre ListView](../../../../docs/framework/wpf/controls/listview-overview.md)