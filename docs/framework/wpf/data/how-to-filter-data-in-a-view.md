---
title: 'Cómo: Filtrar datos en una vista'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [WPF], filtering data
- filtering data in views [WPF]
- data binding [WPF], filtering data in views
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
ms.openlocfilehash: f15bcfd1e3c4175f8b4b97244f120d5edbdec9b8
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453083"
---
# <a name="how-to-filter-data-in-a-view"></a><span data-ttu-id="c37bd-102">Cómo: Filtrar datos en una vista</span><span class="sxs-lookup"><span data-stu-id="c37bd-102">How to: Filter Data in a View</span></span>
<span data-ttu-id="c37bd-103">En este ejemplo se muestra cómo filtrar datos en una vista.</span><span class="sxs-lookup"><span data-stu-id="c37bd-103">This example shows how to filter data in a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c37bd-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c37bd-104">Example</span></span>  
 <span data-ttu-id="c37bd-105">Para crear un filtro, defina un método que proporcione la lógica de filtrado.</span><span class="sxs-lookup"><span data-stu-id="c37bd-105">To create a filter, define a method that provides the filtering logic.</span></span> <span data-ttu-id="c37bd-106">El método se utiliza como devolución de llamada y acepta un parámetro de tipo `object`.</span><span class="sxs-lookup"><span data-stu-id="c37bd-106">The method is used as a callback and accepts a parameter of type `object`.</span></span> <span data-ttu-id="c37bd-107">El método siguiente devuelve todos los objetos `Order` con la propiedad `filled` establecida en "no", filtrando el resto de los objetos.</span><span class="sxs-lookup"><span data-stu-id="c37bd-107">The following method returns all the `Order` objects with the `filled` property set to "No", filtering out the rest of the objects.</span></span>  
  
 [!code-csharp[SortFilter#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="c37bd-108">Después, puede aplicar el filtro, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c37bd-108">You can then apply the filter, as shown in the following example.</span></span> <span data-ttu-id="c37bd-109">En este ejemplo, `myCollectionView` es un objeto <xref:System.Windows.Data.ListCollectionView>.</span><span class="sxs-lookup"><span data-stu-id="c37bd-109">In this example, `myCollectionView` is a <xref:System.Windows.Data.ListCollectionView> object.</span></span>  
  
 [!code-csharp[SortFilter#Filter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 <span data-ttu-id="c37bd-110">Para deshacer el filtrado, puede establecer la propiedad <xref:System.Windows.Data.CollectionView.Filter%2A> en `null`:</span><span class="sxs-lookup"><span data-stu-id="c37bd-110">To undo filtering, you can set the <xref:System.Windows.Data.CollectionView.Filter%2A> property to `null`:</span></span>  
  
 [!code-csharp[SortFilter#Unfilter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 <span data-ttu-id="c37bd-111">Para obtener información sobre cómo crear u obtener una vista, vea [obtener la vista predeterminada de una recolección de datos](how-to-get-the-default-view-of-a-data-collection.md).</span><span class="sxs-lookup"><span data-stu-id="c37bd-111">For information about how to create or obtain a view, see [Get the Default View of a Data Collection](how-to-get-the-default-view-of-a-data-collection.md).</span></span> <span data-ttu-id="c37bd-112">Para obtener el ejemplo completo, vea [ordenar y filtrar elementos en un ejemplo de vista](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/SortFilter).</span><span class="sxs-lookup"><span data-stu-id="c37bd-112">For the complete example, see [Sorting and Filtering Items in a View Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/SortFilter).</span></span>  
  
 <span data-ttu-id="c37bd-113">Si el objeto de vista procede de un objeto <xref:System.Windows.Data.CollectionViewSource>, aplique la lógica de filtrado estableciendo un controlador de eventos para el evento <xref:System.Windows.Data.CollectionViewSource.Filter>.</span><span class="sxs-lookup"><span data-stu-id="c37bd-113">If your view object comes from a <xref:System.Windows.Data.CollectionViewSource> object, you apply filtering logic by setting an event handler for the <xref:System.Windows.Data.CollectionViewSource.Filter> event.</span></span> <span data-ttu-id="c37bd-114">En el ejemplo siguiente, `listingDataView` es una instancia de <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="c37bd-114">In the following example, `listingDataView` is an instance of <xref:System.Windows.Data.CollectionViewSource>.</span></span>  
  
 [!code-csharp[DataBindingLab#10](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 <span data-ttu-id="c37bd-115">A continuación se muestra la implementación del ejemplo de controlador de eventos `ShowOnlyBargainsFilter` Filter.</span><span class="sxs-lookup"><span data-stu-id="c37bd-115">The following shows the implementation of the example `ShowOnlyBargainsFilter` filter event handler.</span></span> <span data-ttu-id="c37bd-116">Este controlador de eventos usa la propiedad <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> para filtrar `AuctionItem` objetos que tienen un `CurrentPrice` de $25 o superior.</span><span class="sxs-lookup"><span data-stu-id="c37bd-116">This event handler uses the <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> property to filter out `AuctionItem` objects that have a `CurrentPrice` of $25 or greater.</span></span>  
  
 [!code-csharp[DataBindingLab#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="c37bd-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c37bd-117">See also</span></span>

- <xref:System.Windows.Data.CollectionView.CanFilter%2A>
- <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>
- [<span data-ttu-id="c37bd-118">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="c37bd-118">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="c37bd-119">Ordenar datos en una vista</span><span class="sxs-lookup"><span data-stu-id="c37bd-119">Sort Data in a View</span></span>](how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="c37bd-120">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="c37bd-120">How-to Topics</span></span>](data-binding-how-to-topics.md)
