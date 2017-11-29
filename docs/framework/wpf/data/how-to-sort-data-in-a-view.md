---
title: "Cómo: Ordenar datos en una vista"
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
- data binding [WPF], sorting data in views
- data binding [WPF], grouping data in views
- grouping data in views [WPF]
- views [WPF], sorting data
- views [WPF], grouping data
- sorting data in views [WPF]
ms.assetid: f4c43578-01b7-4774-a953-acb95a13b94a
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2c39cec8aaf12b268790c19751562b16fa34cfdc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-sort-data-in-a-view"></a><span data-ttu-id="a242f-102">Cómo: Ordenar datos en una vista</span><span class="sxs-lookup"><span data-stu-id="a242f-102">How to: Sort Data in a View</span></span>
<span data-ttu-id="a242f-103">En este ejemplo se describe cómo ordenar datos en una vista.</span><span class="sxs-lookup"><span data-stu-id="a242f-103">This example describes how to sort data in a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a242f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a242f-104">Example</span></span>  
 <span data-ttu-id="a242f-105">En el ejemplo siguiente se crea un sencillo <xref:System.Windows.Controls.ListBox> y <xref:System.Windows.Controls.Button>:</span><span class="sxs-lookup"><span data-stu-id="a242f-105">The following example creates a simple <xref:System.Windows.Controls.ListBox> and a <xref:System.Windows.Controls.Button>:</span></span>  
  
 [!code-xaml[ListBoxSort_snip#HowTo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 <span data-ttu-id="a242f-106">El <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controlador de eventos del botón contiene la lógica necesaria para ordenar los elementos de la <xref:System.Windows.Controls.ListBox> en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="a242f-106">The <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler of the button contains logic to sort the items in the <xref:System.Windows.Controls.ListBox> in the descending order.</span></span> <span data-ttu-id="a242f-107">Para hacer esto porque agregar elementos a un <xref:System.Windows.Controls.ListBox> de esta forma agregarán a la <xref:System.Windows.Controls.ItemCollection> de la <xref:System.Windows.Controls.ListBox>, y <xref:System.Windows.Controls.ItemCollection> se deriva de la <xref:System.Windows.Data.CollectionView> clase.</span><span class="sxs-lookup"><span data-stu-id="a242f-107">You can do this because adding items to a <xref:System.Windows.Controls.ListBox> this way adds them to the <xref:System.Windows.Controls.ItemCollection> of the <xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.ItemCollection> derives from the <xref:System.Windows.Data.CollectionView> class.</span></span> <span data-ttu-id="a242f-108">Si va a enlazar la <xref:System.Windows.Controls.ListBox> a una colección utilizando la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propiedad, puede usar la misma técnica para ordenar.</span><span class="sxs-lookup"><span data-stu-id="a242f-108">If you are binding your <xref:System.Windows.Controls.ListBox> to a collection using the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property, you can use the same technique to sort.</span></span>  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 <span data-ttu-id="a242f-109">Siempre y cuando tenga una referencia al objeto de vista, puede usar la misma técnica para ordenar el contenido de otras vistas de colección.</span><span class="sxs-lookup"><span data-stu-id="a242f-109">As long as you have a reference to the view object, you can use the same technique to sort the content of other collection views.</span></span> <span data-ttu-id="a242f-110">Para obtener un ejemplo de cómo obtener una vista, consulte [obtener la vista predeterminada de una recolección de datos](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).</span><span class="sxs-lookup"><span data-stu-id="a242f-110">For an example of how to obtain a view, see [Get the Default View of a Data Collection](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).</span></span> <span data-ttu-id="a242f-111">Para obtener otro ejemplo, vea [ordenar un GridView columna cuando un encabezado se hace clic en](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).</span><span class="sxs-lookup"><span data-stu-id="a242f-111">For another example, see [Sort a GridView Column When a Header Is Clicked](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).</span></span> <span data-ttu-id="a242f-112">Para obtener más información acerca de las vistas, consulte enlazar a colecciones en [información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a242f-112">For more information about views, see Binding to Collections in [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="a242f-113">Para obtener un ejemplo de cómo aplicar la lógica de ordenación en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], consulte [ordenar y el grupo de datos mediante una vista en XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="a242f-113">For an example of how to apply sorting logic in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], see [Sort and Group Data Using a View in XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a242f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a242f-114">See Also</span></span>  
 <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>  
 [<span data-ttu-id="a242f-115">Ordenar una columna de GridView cuando se hace clic en un encabezado</span><span class="sxs-lookup"><span data-stu-id="a242f-115">Sort a GridView Column When a Header Is Clicked</span></span>](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)  
 [<span data-ttu-id="a242f-116">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="a242f-116">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="a242f-117">Filtrar datos en una vista</span><span class="sxs-lookup"><span data-stu-id="a242f-117">Filter Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [<span data-ttu-id="a242f-118">Temas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="a242f-118">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
