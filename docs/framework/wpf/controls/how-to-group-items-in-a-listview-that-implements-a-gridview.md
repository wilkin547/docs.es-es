---
title: Filtrar Agrupar elementos en un control ListView que implementa un modo GridView
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], grouping items with GridViews
- grouping items in ListViews implementing GridViews [WPF]
- GridView controls [WPF], grouping items
ms.assetid: eebef25b-ddc6-424e-a66d-ea228d1bf33d
ms.openlocfilehash: b3dd6891976a942b299c87fca25e430e9ee59a51
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59177676"
---
# <a name="how-to-group-items-in-a-listview-that-implements-a-gridview"></a>Filtrar Agrupar elementos en un control ListView que implementa un modo GridView
En este ejemplo se muestra cómo mostrar los grupos de elementos de la <xref:System.Windows.Controls.GridView> modo de vista de un <xref:System.Windows.Controls.ListView> control.  
  
## <a name="example"></a>Ejemplo  
 Para mostrar los grupos de elementos en un <xref:System.Windows.Controls.ListView>, defina un <xref:System.Windows.Data.CollectionViewSource>. El ejemplo siguiente se muestra un <xref:System.Windows.Data.CollectionViewSource> que agrupa los elementos de datos según el valor de la `Catalog` campo de datos.  
  
 [!code-xaml[GridViewWithGroups#GroupingCollectionViewSource](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#groupingcollectionviewsource)]  
  
 El ejemplo siguiente se establece la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> para el <xref:System.Windows.Controls.ListView> a la <xref:System.Windows.Data.CollectionViewSource> que define el ejemplo anterior. El ejemplo también define un <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> que implementa un <xref:System.Windows.Controls.Expander> control.  
  
 [!code-xaml[GridViewWithGroups#ListViewGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewgroups)]  
[!code-xaml[GridViewWithGroups#ListViewEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewend)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Temas "Cómo..."](listview-how-to-topics.md)
- [Información general sobre ListView](listview-overview.md)
- [Información general sobre GridView](gridview-overview.md)
