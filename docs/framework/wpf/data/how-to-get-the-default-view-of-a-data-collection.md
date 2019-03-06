---
title: Procedimiento Obtener la vista predeterminada de una recolección de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
ms.openlocfilehash: 28a21aae7f8a08efebfd16bacd2a2d82b04de0c1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360074"
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a><span data-ttu-id="a5f1f-102">Filtrar Obtener la vista predeterminada de una recolección de datos</span><span class="sxs-lookup"><span data-stu-id="a5f1f-102">How to: Get the Default View of a Data Collection</span></span>
<span data-ttu-id="a5f1f-103">Las vistas permiten la misma colección de datos a verse de maneras diferentes, dependiendo de la ordenación, filtrado o criterio de agrupación.</span><span class="sxs-lookup"><span data-stu-id="a5f1f-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping criteria.</span></span> <span data-ttu-id="a5f1f-104">Cada colección tiene una vista compartida de forma predeterminada, que se usa como origen de enlace real cuando un enlace especifica una colección como origen.</span><span class="sxs-lookup"><span data-stu-id="a5f1f-104">Every collection has one shared default view, which is used as the actual binding source when a binding specifies a collection as its source.</span></span> <span data-ttu-id="a5f1f-105">En este ejemplo se muestra cómo obtener la vista predeterminada de una colección.</span><span class="sxs-lookup"><span data-stu-id="a5f1f-105">This example shows how to get the default view of a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5f1f-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a5f1f-106">Example</span></span>  
 <span data-ttu-id="a5f1f-107">Para crear la vista, necesita una referencia de objeto a la colección.</span><span class="sxs-lookup"><span data-stu-id="a5f1f-107">To create the view, you need an object reference to the collection.</span></span> <span data-ttu-id="a5f1f-108">Este objeto de datos puede obtenerse haciendo referencia a su propio objeto de código subyacente, obteniendo el contexto de datos, obteniendo una propiedad del origen de datos, u obteniendo una propiedad del enlace.</span><span class="sxs-lookup"><span data-stu-id="a5f1f-108">This data object can be obtained by referencing your own code-behind object, by getting the data context, by getting a property of the data source, or by getting a property of the binding.</span></span> <span data-ttu-id="a5f1f-109">En este ejemplo se muestra cómo obtener el <xref:System.Windows.FrameworkElement.DataContext%2A> de un objeto de datos y uso para obtener directamente la colección predeterminada ver de esta colección.</span><span class="sxs-lookup"><span data-stu-id="a5f1f-109">This example shows how to get the <xref:System.Windows.FrameworkElement.DataContext%2A> of a data object and use it to directly obtain the default collection view for this collection.</span></span>  
  
 [!code-csharp[CollectionView#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="a5f1f-110">En este ejemplo, el elemento raíz es un <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="a5f1f-110">In this example, the root element is a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="a5f1f-111">El <xref:System.Windows.FrameworkElement.DataContext%2A> está establecido en *myDataSource*, que hace referencia a un proveedor de datos que es un <xref:System.Collections.ObjectModel.ObservableCollection%601> de *orden* objetos.</span><span class="sxs-lookup"><span data-stu-id="a5f1f-111">The <xref:System.Windows.FrameworkElement.DataContext%2A> is set to *myDataSource*, which refers to a data provider that is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of *Order* objects.</span></span>  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 <span data-ttu-id="a5f1f-112">Como alternativa, puede crear instancias y enlazar a su propia vista de colección mediante el <xref:System.Windows.Data.CollectionViewSource> clase.</span><span class="sxs-lookup"><span data-stu-id="a5f1f-112">Alternatively, you can instantiate and bind to your own collection view using the <xref:System.Windows.Data.CollectionViewSource> class.</span></span> <span data-ttu-id="a5f1f-113">Esta vista de colección solo se comparte entre los controles que se enlazan directamente a él.</span><span class="sxs-lookup"><span data-stu-id="a5f1f-113">This collection view is only shared by controls that bind to it directly.</span></span> <span data-ttu-id="a5f1f-114">Para obtener un ejemplo, vea cómo crear una sección de vista en el [Data Binding Overview](data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a5f1f-114">For an example, see the How to Create a View section in the [Data Binding Overview](data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="a5f1f-115">Para obtener ejemplos de la funcionalidad proporcionada por una vista de colección, consulte [ordenar datos en una vista](how-to-sort-data-in-a-view.md), [filtrar los datos en una vista](how-to-filter-data-in-a-view.md), y [navegar por los objetos de una colección de datos mediante CollectionView](how-to-navigate-through-the-objects-in-a-data-collectionview.md).</span><span class="sxs-lookup"><span data-stu-id="a5f1f-115">For examples of the functionality provided by a collection view, see [Sort Data in a View](how-to-sort-data-in-a-view.md), [Filter Data in a View](how-to-filter-data-in-a-view.md), and [Navigate Through the Objects in a Data CollectionView](how-to-navigate-through-the-objects-in-a-data-collectionview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5f1f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5f1f-116">See also</span></span>
- [<span data-ttu-id="a5f1f-117">Ordenar y agrupar datos mediante una vista en XAML</span><span class="sxs-lookup"><span data-stu-id="a5f1f-117">Sort and Group Data Using a View in XAML</span></span>](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [<span data-ttu-id="a5f1f-118">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="a5f1f-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
