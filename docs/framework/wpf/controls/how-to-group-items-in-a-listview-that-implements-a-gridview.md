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
# <a name="how-to-group-items-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="43627-102">Filtrar Agrupar elementos en un control ListView que implementa un modo GridView</span><span class="sxs-lookup"><span data-stu-id="43627-102">How to: Group Items in a ListView That Implements a GridView</span></span>
<span data-ttu-id="43627-103">En este ejemplo se muestra cómo mostrar los grupos de elementos de la <xref:System.Windows.Controls.GridView> modo de vista de un <xref:System.Windows.Controls.ListView> control.</span><span class="sxs-lookup"><span data-stu-id="43627-103">This example shows how to display groups of items in the <xref:System.Windows.Controls.GridView> view mode of a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43627-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="43627-104">Example</span></span>  
 <span data-ttu-id="43627-105">Para mostrar los grupos de elementos en un <xref:System.Windows.Controls.ListView>, defina un <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="43627-105">To display groups of items in a <xref:System.Windows.Controls.ListView>, define a <xref:System.Windows.Data.CollectionViewSource>.</span></span> <span data-ttu-id="43627-106">El ejemplo siguiente se muestra un <xref:System.Windows.Data.CollectionViewSource> que agrupa los elementos de datos según el valor de la `Catalog` campo de datos.</span><span class="sxs-lookup"><span data-stu-id="43627-106">The following example shows a <xref:System.Windows.Data.CollectionViewSource> that groups data items according to the value of the `Catalog` data field.</span></span>  
  
 [!code-xaml[GridViewWithGroups#GroupingCollectionViewSource](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#groupingcollectionviewsource)]  
  
 <span data-ttu-id="43627-107">El ejemplo siguiente se establece la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> para el <xref:System.Windows.Controls.ListView> a la <xref:System.Windows.Data.CollectionViewSource> que define el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="43627-107">The following example sets the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.ListView> to the <xref:System.Windows.Data.CollectionViewSource> that the previous example defines.</span></span> <span data-ttu-id="43627-108">El ejemplo también define un <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> que implementa un <xref:System.Windows.Controls.Expander> control.</span><span class="sxs-lookup"><span data-stu-id="43627-108">The example also defines a <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> that implements an <xref:System.Windows.Controls.Expander> control.</span></span>  
  
 [!code-xaml[GridViewWithGroups#ListViewGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewgroups)]  
[!code-xaml[GridViewWithGroups#ListViewEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewend)]  
  
## <a name="see-also"></a><span data-ttu-id="43627-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="43627-109">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="43627-110">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="43627-110">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="43627-111">Información general sobre ListView</span><span class="sxs-lookup"><span data-stu-id="43627-111">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="43627-112">Información general sobre GridView</span><span class="sxs-lookup"><span data-stu-id="43627-112">GridView Overview</span></span>](gridview-overview.md)
