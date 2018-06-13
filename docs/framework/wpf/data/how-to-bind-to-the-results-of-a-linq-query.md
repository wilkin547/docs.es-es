---
title: 'Cómo: Enlazar a los resultados de una consulta LINQ'
ms.date: 03/30/2017
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
ms.openlocfilehash: d374bb69b6b7e022497403b9591b27e9ad7e2395
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554998"
---
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a><span data-ttu-id="5955a-102">Cómo: Enlazar a los resultados de una consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="5955a-102">How to: Bind to the Results of a LINQ Query</span></span>
<span data-ttu-id="5955a-103">Este ejemplo muestra cómo ejecutar una consulta LINQ y, a continuación, enlazar a los resultados.</span><span class="sxs-lookup"><span data-stu-id="5955a-103">This example demonstrates how to run a LINQ query and then bind to the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5955a-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5955a-104">Example</span></span>  
 <span data-ttu-id="5955a-105">En el ejemplo siguiente se crea dos cuadros de lista.</span><span class="sxs-lookup"><span data-stu-id="5955a-105">The following example creates two list boxes.</span></span> <span data-ttu-id="5955a-106">El primer cuadro de lista contiene tres elementos de lista.</span><span class="sxs-lookup"><span data-stu-id="5955a-106">The first list box contains three list items.</span></span>  
  
 [!code-xaml[LinqExample#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="5955a-107">Seleccionar un elemento en el primer cuadro de lista, invoca el controlador de eventos siguiente.</span><span class="sxs-lookup"><span data-stu-id="5955a-107">Selecting an item from the first list box invokes the following event handler.</span></span> <span data-ttu-id="5955a-108">En este ejemplo, `Tasks` es una colección de `Task` objetos.</span><span class="sxs-lookup"><span data-stu-id="5955a-108">In this example, `Tasks` is a collection of `Task` objects.</span></span> <span data-ttu-id="5955a-109">El `Task` clase tiene una propiedad denominada `Priority`.</span><span class="sxs-lookup"><span data-stu-id="5955a-109">The `Task` class has a property named `Priority`.</span></span> <span data-ttu-id="5955a-110">Este controlador de eventos ejecuta una consulta LINQ que devuelve la colección de `Task` objetos que tienen el valor de prioridad seleccionado y, a continuación, se establece como el <xref:System.Windows.FrameworkElement.DataContext%2A>:</span><span class="sxs-lookup"><span data-stu-id="5955a-110">This event handler runs a LINQ query that returns the collection of `Task` objects that have the selected priority value, and then sets that as the <xref:System.Windows.FrameworkElement.DataContext%2A>:</span></span>  
  
 [!code-csharp[LinqExample#Using](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]  
[!code-csharp[LinqExample#Tasks](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]  
[!code-csharp[LinqExample#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]  
  
 <span data-ttu-id="5955a-111">El segundo cuadro de lista se enlaza a esa colección porque su <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> valor se establece en `{Binding}`.</span><span class="sxs-lookup"><span data-stu-id="5955a-111">The second list box binds to that collection because its <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> value is set to `{Binding}`.</span></span> <span data-ttu-id="5955a-112">Como resultado, muestra la colección devuelta (en función de la `myTaskTemplate` <xref:System.Windows.DataTemplate>).</span><span class="sxs-lookup"><span data-stu-id="5955a-112">As a result, it displays the returned collection (based on the `myTaskTemplate`<xref:System.Windows.DataTemplate>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5955a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5955a-113">See Also</span></span>  
 [<span data-ttu-id="5955a-114">Hacer que los datos estén disponibles para el enlace en XAML</span><span class="sxs-lookup"><span data-stu-id="5955a-114">Make Data Available for Binding in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)  
 [<span data-ttu-id="5955a-115">Enlazar a una colección y mostrar información basada en la selección</span><span class="sxs-lookup"><span data-stu-id="5955a-115">Bind to a Collection and Display Information Based on Selection</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)  
 [<span data-ttu-id="5955a-116">Novedades de WPF versión 4.5</span><span class="sxs-lookup"><span data-stu-id="5955a-116">What's New in WPF Version 4.5</span></span>](../../../../docs/framework/wpf/getting-started/whats-new.md)  
 [<span data-ttu-id="5955a-117">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="5955a-117">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="5955a-118">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="5955a-118">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
