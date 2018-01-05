---
title: "Cómo: Agrupar elementos en un control ListView que implementa un modo GridView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView controls [WPF], grouping items with GridViews
- grouping items in ListViews implementing GridViews [WPF]
- GridView controls [WPF], grouping items
ms.assetid: eebef25b-ddc6-424e-a66d-ea228d1bf33d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8a97a6c85036a6daf4e8c908186953f9a75f952a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-group-items-in-a-listview-that-implements-a-gridview"></a>Cómo: Agrupar elementos en un control ListView que implementa un modo GridView
Este ejemplo muestra cómo mostrar grupos de elementos en el <xref:System.Windows.Controls.GridView> modo de vista de un <xref:System.Windows.Controls.ListView> control.  
  
## <a name="example"></a>Ejemplo  
 Para mostrar grupos de elementos en una <xref:System.Windows.Controls.ListView>, defina un <xref:System.Windows.Data.CollectionViewSource>. El ejemplo siguiente muestra un <xref:System.Windows.Data.CollectionViewSource> que agrupa los elementos de datos según el valor de la `Catalog` campo de datos.  
  
 [!code-xaml[GridViewWithGroups#GroupingCollectionViewSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#groupingcollectionviewsource)]  
  
 El ejemplo siguiente se establece la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> para el <xref:System.Windows.Controls.ListView> a la <xref:System.Windows.Data.CollectionViewSource> que define el ejemplo anterior. El ejemplo también define un <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> que implementa un <xref:System.Windows.Controls.Expander> control.  
  
 [!code-xaml[GridViewWithGroups#ListViewGroups](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewgroups)]  
[!code-xaml[GridViewWithGroups#ListViewEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewend)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Información general sobre ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Información general sobre GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
