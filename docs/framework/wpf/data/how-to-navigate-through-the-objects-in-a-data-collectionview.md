---
title: Procedimiento Navegar por los objetos de una colección de datos mediante CollectionView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CollectionView [WPF], navigating through objects
- data binding [WPF], navigating through objects in data CollectionView
- navigating through objects in data CollectionView [WPF]
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
ms.openlocfilehash: 1507ab4db0c91b670d8bca754f6fd67d887c7041
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61931515"
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a><span data-ttu-id="e7f2c-102">Procedimiento Navegar por los objetos de una colección de datos mediante CollectionView</span><span class="sxs-lookup"><span data-stu-id="e7f2c-102">How to: Navigate Through the Objects in a Data CollectionView</span></span>
<span data-ttu-id="e7f2c-103">Las vistas permiten la misma colección de datos a verse de maneras diferentes, dependiendo de ordenar, filtrar o agrupar.</span><span class="sxs-lookup"><span data-stu-id="e7f2c-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping.</span></span> <span data-ttu-id="e7f2c-104">Las vistas también proporcionan un concepto de puntero de registro actual y permiten mover el puntero.</span><span class="sxs-lookup"><span data-stu-id="e7f2c-104">Views also provide a current record pointer concept and enable moving the pointer.</span></span> <span data-ttu-id="e7f2c-105">En este ejemplo se muestra cómo obtener el objeto actual, así como navegar por los objetos en una recopilación de datos mediante la funcionalidad proporcionada en el <xref:System.Windows.Data.CollectionView> clase.</span><span class="sxs-lookup"><span data-stu-id="e7f2c-105">This example shows how to get the current object as well as navigate through the objects in a data collection using the functionality provided in the <xref:System.Windows.Data.CollectionView> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7f2c-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e7f2c-106">Example</span></span>  
 <span data-ttu-id="e7f2c-107">En este ejemplo, `myCollectionView` es un <xref:System.Windows.Data.CollectionView> objeto que es una vista a través de una colección enlazada.</span><span class="sxs-lookup"><span data-stu-id="e7f2c-107">In this example, `myCollectionView` is a <xref:System.Windows.Data.CollectionView> object that is a view over a bound collection.</span></span>  
  
 <span data-ttu-id="e7f2c-108">En el ejemplo siguiente, `OnButton` es un controlador de eventos para el `Previous` y `Next` botones en una aplicación, que son los botones que permiten al usuario navegar por la recopilación de datos.</span><span class="sxs-lookup"><span data-stu-id="e7f2c-108">In the following example, `OnButton` is an event handler for the `Previous` and `Next` buttons in an application, which are buttons that allow the user to navigate the data collection.</span></span> <span data-ttu-id="e7f2c-109">Tenga en cuenta que el <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> y <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> propiedades de informes si el puntero de registro actual ha llegado al comienzo y final de la lista respectivamente hasta que <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> y <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> pueden llamarse como corresponda.</span><span class="sxs-lookup"><span data-stu-id="e7f2c-109">Note that the <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> and <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> properties report whether the current record pointer has come to the beginning and the end of the list respectively so that <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> and <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> can be called as appropriately.</span></span>  
  
 <span data-ttu-id="e7f2c-110">El <xref:System.Windows.Data.CollectionView.CurrentItem%2A> propiedad de la vista se convierte como un `Order` para devolver el elemento de orden actual de la colección.</span><span class="sxs-lookup"><span data-stu-id="e7f2c-110">The <xref:System.Windows.Data.CollectionView.CurrentItem%2A> property of the view is cast as an `Order` to return the current order item in the collection.</span></span>  
  
 [!code-csharp[CollectionView#OnButton](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a><span data-ttu-id="e7f2c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7f2c-111">See also</span></span>

- [<span data-ttu-id="e7f2c-112">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="e7f2c-112">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="e7f2c-113">Ordenar datos en una vista</span><span class="sxs-lookup"><span data-stu-id="e7f2c-113">Sort Data in a View</span></span>](how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="e7f2c-114">Filtrar datos en una vista</span><span class="sxs-lookup"><span data-stu-id="e7f2c-114">Filter Data in a View</span></span>](how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="e7f2c-115">Ordenar y agrupar datos mediante una vista en XAML</span><span class="sxs-lookup"><span data-stu-id="e7f2c-115">Sort and Group Data Using a View in XAML</span></span>](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [<span data-ttu-id="e7f2c-116">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="e7f2c-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
