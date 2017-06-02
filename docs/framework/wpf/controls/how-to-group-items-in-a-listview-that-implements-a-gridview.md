---
title: "C&#243;mo: Agrupar elementos en un control ListView que implementa un modo GridView | Microsoft Docs"
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
  - "GridView (controles), agrupar elementos"
  - "agrupar elementos en ListViews con GridViews"
  - "ListView (controles), agrupar elementos con GridViews"
ms.assetid: eebef25b-ddc6-424e-a66d-ea228d1bf33d
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Agrupar elementos en un control ListView que implementa un modo GridView
En este ejemplo se muestra cómo mostrar grupos de elementos en el modo de vista <xref:System.Windows.Controls.GridView> de un control <xref:System.Windows.Controls.ListView>.  
  
## Ejemplo  
 Para mostrar grupos de elementos en un objeto <xref:System.Windows.Controls.ListView>, defina <xref:System.Windows.Data.CollectionViewSource>.  En el ejemplo siguiente se muestra un objeto <xref:System.Windows.Data.CollectionViewSource> que agrupa los elementos de datos según el valor del campo de datos `Catalog`.  
  
 [!code-xml[GridViewWithGroups#GroupingCollectionViewSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#groupingcollectionviewsource)]  
  
 En el ejemplo siguiente se establece la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> para el objeto <xref:System.Windows.Controls.ListView> en el objeto <xref:System.Windows.Data.CollectionViewSource> definido por el ejemplo anterior.  El ejemplo también define un objeto <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> que implementa un control <xref:System.Windows.Controls.Expander>.  
  
 [!code-xml[GridViewWithGroups#ListViewGroups](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewgroups)]  
[!code-xml[GridViewWithGroups#ListViewEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewend)]  
  
## Vea también  
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [Información general sobre ListView](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [Información general sobre GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)