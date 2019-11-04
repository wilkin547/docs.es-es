---
title: 'Cómo: Obtener la vista predeterminada de una recolección de datos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
ms.openlocfilehash: e82d252ed82e4d2e6d641e8b60e890cc93bb0427
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459117"
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a><span data-ttu-id="e3783-102">Cómo: Obtener la vista predeterminada de una recolección de datos</span><span class="sxs-lookup"><span data-stu-id="e3783-102">How to: Get the Default View of a Data Collection</span></span>
<span data-ttu-id="e3783-103">Las vistas permiten ver la misma recopilación de datos de maneras diferentes, en función de los criterios de ordenación, filtrado o agrupación.</span><span class="sxs-lookup"><span data-stu-id="e3783-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping criteria.</span></span> <span data-ttu-id="e3783-104">Cada colección tiene una vista predeterminada compartida, que se utiliza como el origen de Enlace real cuando un enlace especifica una colección como su origen.</span><span class="sxs-lookup"><span data-stu-id="e3783-104">Every collection has one shared default view, which is used as the actual binding source when a binding specifies a collection as its source.</span></span> <span data-ttu-id="e3783-105">En este ejemplo se muestra cómo obtener la vista predeterminada de una colección.</span><span class="sxs-lookup"><span data-stu-id="e3783-105">This example shows how to get the default view of a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3783-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e3783-106">Example</span></span>  
 <span data-ttu-id="e3783-107">Para crear la vista, necesita una referencia de objeto a la colección.</span><span class="sxs-lookup"><span data-stu-id="e3783-107">To create the view, you need an object reference to the collection.</span></span> <span data-ttu-id="e3783-108">Este objeto de datos se puede obtener haciendo referencia a su propio objeto de código subyacente, obteniendo el contexto de datos, obteniendo una propiedad del origen de datos o obteniendo una propiedad del enlace.</span><span class="sxs-lookup"><span data-stu-id="e3783-108">This data object can be obtained by referencing your own code-behind object, by getting the data context, by getting a property of the data source, or by getting a property of the binding.</span></span> <span data-ttu-id="e3783-109">En este ejemplo se muestra cómo obtener el <xref:System.Windows.FrameworkElement.DataContext%2A> de un objeto de datos y cómo utilizarlo para obtener directamente la vista de colección predeterminada de esta colección.</span><span class="sxs-lookup"><span data-stu-id="e3783-109">This example shows how to get the <xref:System.Windows.FrameworkElement.DataContext%2A> of a data object and use it to directly obtain the default collection view for this collection.</span></span>  
  
 [!code-csharp[CollectionView#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="e3783-110">En este ejemplo, el elemento raíz es un <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="e3783-110">In this example, the root element is a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="e3783-111">La <xref:System.Windows.FrameworkElement.DataContext%2A> se establece en mi *DataSource*, que hace referencia a un proveedor de datos que es una <xref:System.Collections.ObjectModel.ObservableCollection%601> de objetos de *pedido* .</span><span class="sxs-lookup"><span data-stu-id="e3783-111">The <xref:System.Windows.FrameworkElement.DataContext%2A> is set to *myDataSource*, which refers to a data provider that is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of *Order* objects.</span></span>  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 <span data-ttu-id="e3783-112">Como alternativa, puede crear una instancia de y enlazar a su propia vista de colección mediante la <xref:System.Windows.Data.CollectionViewSource> clase.</span><span class="sxs-lookup"><span data-stu-id="e3783-112">Alternatively, you can instantiate and bind to your own collection view using the <xref:System.Windows.Data.CollectionViewSource> class.</span></span> <span data-ttu-id="e3783-113">Esta vista de colección solo la comparten los controles que se enlazan a ella directamente.</span><span class="sxs-lookup"><span data-stu-id="e3783-113">This collection view is only shared by controls that bind to it directly.</span></span> <span data-ttu-id="e3783-114">Para obtener un ejemplo, vea la sección Cómo crear una vista en [información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e3783-114">For an example, see the How to Create a View section in the [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="e3783-115">Para obtener ejemplos de la funcionalidad proporcionada por una vista de colección, vea [ordenar datos en una vista](how-to-sort-data-in-a-view.md), [filtrar datos en una vista](how-to-filter-data-in-a-view.md)y [navegar por los objetos de una colección de datos](how-to-navigate-through-the-objects-in-a-data-collectionview.md).</span><span class="sxs-lookup"><span data-stu-id="e3783-115">For examples of the functionality provided by a collection view, see [Sort Data in a View](how-to-sort-data-in-a-view.md), [Filter Data in a View](how-to-filter-data-in-a-view.md), and [Navigate Through the Objects in a Data CollectionView](how-to-navigate-through-the-objects-in-a-data-collectionview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3783-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3783-116">See also</span></span>

- [<span data-ttu-id="e3783-117">Ordenar y agrupar datos mediante una vista en XAML</span><span class="sxs-lookup"><span data-stu-id="e3783-117">Sort and Group Data Using a View in XAML</span></span>](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [<span data-ttu-id="e3783-118">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="e3783-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
