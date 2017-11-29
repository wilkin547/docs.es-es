---
title: "Cómo: Navegar por los objetos de una colección de datos mediante CollectionView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CollectionView [WPF], navigating through objects
- data binding [WPF], navigating through objects in data CollectionView
- navigating through objects in data CollectionView [WPF]
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f20881ed452f1ec78381d17a32b4cc2c77305e0e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a><span data-ttu-id="2a5c5-102">Cómo: Navegar por los objetos de una colección de datos mediante CollectionView</span><span class="sxs-lookup"><span data-stu-id="2a5c5-102">How to: Navigate Through the Objects in a Data CollectionView</span></span>
<span data-ttu-id="2a5c5-103">Las vistas permiten la misma colección de datos a verse de maneras diferentes, dependiendo de ordenar, filtrar o agrupar.</span><span class="sxs-lookup"><span data-stu-id="2a5c5-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping.</span></span> <span data-ttu-id="2a5c5-104">Vistas también proporcionan un concepto de puntero de registro actual y habilitan el movimiento del puntero.</span><span class="sxs-lookup"><span data-stu-id="2a5c5-104">Views also provide a current record pointer concept and enable moving the pointer.</span></span> <span data-ttu-id="2a5c5-105">Este ejemplo muestra cómo obtener el objeto actual, así como navegar por los objetos en una recopilación de datos mediante la funcionalidad proporcionada en el <xref:System.Windows.Data.CollectionView> clase.</span><span class="sxs-lookup"><span data-stu-id="2a5c5-105">This example shows how to get the current object as well as navigate through the objects in a data collection using the functionality provided in the <xref:System.Windows.Data.CollectionView> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a5c5-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2a5c5-106">Example</span></span>  
 <span data-ttu-id="2a5c5-107">En este ejemplo, `myCollectionView` es un <xref:System.Windows.Data.CollectionView> objeto que es una vista a través de una colección enlazada.</span><span class="sxs-lookup"><span data-stu-id="2a5c5-107">In this example, `myCollectionView` is a <xref:System.Windows.Data.CollectionView> object that is a view over a bound collection.</span></span>  
  
 <span data-ttu-id="2a5c5-108">En el ejemplo siguiente, `OnButton` es un controlador de eventos para el `Previous` y `Next` botones en una aplicación, que son botones que permiten al usuario navegar por la recolección de datos.</span><span class="sxs-lookup"><span data-stu-id="2a5c5-108">In the following example, `OnButton` is an event handler for the `Previous` and `Next` buttons in an application, which are buttons that allow the user to navigate the data collection.</span></span> <span data-ttu-id="2a5c5-109">Tenga en cuenta que la <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> y <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> propiedades de informes si el puntero de registro actual ha llegado al principio y el final de la lista respectivamente así que <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> y <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> pueden llamarse como corresponda.</span><span class="sxs-lookup"><span data-stu-id="2a5c5-109">Note that the <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> and <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> properties report whether the current record pointer has come to the beginning and the end of the list respectively so that <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> and <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> can be called as appropriately.</span></span>  
  
 <span data-ttu-id="2a5c5-110">El <xref:System.Windows.Data.CollectionView.CurrentItem%2A> propiedad de la vista se convierte como un `Order` para devolver el elemento actual de la colección.</span><span class="sxs-lookup"><span data-stu-id="2a5c5-110">The <xref:System.Windows.Data.CollectionView.CurrentItem%2A> property of the view is cast as an `Order` to return the current order item in the collection.</span></span>  
  
 [!code-csharp[CollectionView#OnButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a><span data-ttu-id="2a5c5-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a5c5-111">See Also</span></span>  
 [<span data-ttu-id="2a5c5-112">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="2a5c5-112">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="2a5c5-113">Ordenar datos en una vista</span><span class="sxs-lookup"><span data-stu-id="2a5c5-113">Sort Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [<span data-ttu-id="2a5c5-114">Filtrar datos en una vista</span><span class="sxs-lookup"><span data-stu-id="2a5c5-114">Filter Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [<span data-ttu-id="2a5c5-115">Ordenar y agrupar datos mediante una vista en XAML</span><span class="sxs-lookup"><span data-stu-id="2a5c5-115">Sort and Group Data Using a View in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)  
 [<span data-ttu-id="2a5c5-116">Temas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="2a5c5-116">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
