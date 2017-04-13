---
title: "C&#243;mo: Cambiar la alineaci&#243;n horizontal de una columna en un control ListView | Microsoft Docs"
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
  - "ListView (controles), alineación horizontal"
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# C&#243;mo: Cambiar la alineaci&#243;n horizontal de una columna en un control ListView
De forma predeterminada, el contenido de cada columna de un elemento <xref:System.Windows.Controls.ListViewItem> está alineado a la izquierda.  Para cambiar la alineación de cada columna, proporcione una <xref:System.Windows.DataTemplate> y establezca la propiedad <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> del elemento dentro del objeto <xref:System.Windows.DataTemplate>.  En este tema se muestra cómo el control <xref:System.Windows.Controls.ListView> alinea su contenido de forma predeterminada y cómo cambiar la alineación de una columna del control <xref:System.Windows.Controls.ListView>.  
  
## Ejemplo  
 En el ejemplo siguiente, los datos de las columnas `Title` e `ISBN` se alinean a la izquierda.  
  
 [!code-xml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 Para cambiar la alineación de la columna `ISBN`, hay que especificar que la propiedad <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> de cada control <xref:System.Windows.Controls.ListViewItem> es <xref:System.Windows.HorizontalAlignment> para que los elementos de cada control <xref:System.Windows.Controls.ListViewItem> puedan abarcar el ancho completo de cada columna o situarse a lo largo de él.  Como <xref:System.Windows.Controls.ListView> está enlazado a un origen de datos, es preciso crear un estilo que establezca la propiedad <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>.  A continuación, tiene que utilizar <xref:System.Windows.DataTemplate> para mostrar el contenido, en lugar de utilizar la propiedad <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>.  Para mostrar el valor `ISBN` de cada plantilla, <xref:System.Windows.DataTemplate> puede contener únicamente un control <xref:System.Windows.Controls.TextBlock> cuya propiedad <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> esté establecida en <xref:System.Windows.HorizontalAlignment>.  
  
 En el ejemplo siguiente se define el estilo y el objeto <xref:System.Windows.DataTemplate> necesarios para alinear a la derecha la columna `ISBN` y se cambia <xref:System.Windows.Controls.GridViewColumn> de modo que haga referencia a <xref:System.Windows.DataTemplate>.  
  
 [!code-xml[ListViewHowTos#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xml[ListViewHowTos#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## Vea también  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Información general sobre plantillas de datos](../../../../docs/framework/wpf/data/data-templating-overview.md)   
 [Enlazar a datos XML mediante XMLDataProvider y consultas XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)   
 [Información general sobre ListView](../../../../docs/framework/wpf/controls/listview-overview.md)