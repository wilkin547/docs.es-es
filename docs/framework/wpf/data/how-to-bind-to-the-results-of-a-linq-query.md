---
title: "Cómo: Enlazar a los resultados de una consulta LINQ"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e77a0c698dae0330877c54422c15e14c82376891
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a><span data-ttu-id="297f0-102">Cómo: Enlazar a los resultados de una consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="297f0-102">How to: Bind to the Results of a LINQ Query</span></span>
<span data-ttu-id="297f0-103">Este ejemplo muestra cómo ejecutar una consulta LINQ y, a continuación, enlazar a los resultados.</span><span class="sxs-lookup"><span data-stu-id="297f0-103">This example demonstrates how to run a LINQ query and then bind to the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="297f0-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="297f0-104">Example</span></span>  
 <span data-ttu-id="297f0-105">En el ejemplo siguiente se crea dos cuadros de lista.</span><span class="sxs-lookup"><span data-stu-id="297f0-105">The following example creates two list boxes.</span></span> <span data-ttu-id="297f0-106">El primer cuadro de lista contiene tres elementos de lista.</span><span class="sxs-lookup"><span data-stu-id="297f0-106">The first list box contains three list items.</span></span>  
  
 [!code-xaml[LinqExample#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="297f0-107">Seleccionar un elemento en el primer cuadro de lista, invoca el controlador de eventos siguiente.</span><span class="sxs-lookup"><span data-stu-id="297f0-107">Selecting an item from the first list box invokes the following event handler.</span></span> <span data-ttu-id="297f0-108">En este ejemplo, `Tasks` es una colección de `Task` objetos.</span><span class="sxs-lookup"><span data-stu-id="297f0-108">In this example, `Tasks` is a collection of `Task` objects.</span></span> <span data-ttu-id="297f0-109">El `Task` clase tiene una propiedad denominada `Priority`.</span><span class="sxs-lookup"><span data-stu-id="297f0-109">The `Task` class has a property named `Priority`.</span></span> <span data-ttu-id="297f0-110">Este controlador de eventos ejecuta una consulta LINQ que devuelve la colección de `Task` objetos que tienen el valor de prioridad seleccionado y, a continuación, se establece como el <xref:System.Windows.FrameworkElement.DataContext%2A>:</span><span class="sxs-lookup"><span data-stu-id="297f0-110">This event handler runs a LINQ query that returns the collection of `Task` objects that have the selected priority value, and then sets that as the <xref:System.Windows.FrameworkElement.DataContext%2A>:</span></span>  
  
 [!code-csharp[LinqExample#Using](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]  
[!code-csharp[LinqExample#Tasks](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]  
[!code-csharp[LinqExample#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]  
  
 <span data-ttu-id="297f0-111">El segundo cuadro de lista se enlaza a esa colección porque su <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> valor se establece en `{Binding}`.</span><span class="sxs-lookup"><span data-stu-id="297f0-111">The second list box binds to that collection because its <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> value is set to `{Binding}`.</span></span> <span data-ttu-id="297f0-112">Como resultado, muestra la colección devuelta (en función de la `myTaskTemplate` <xref:System.Windows.DataTemplate>).</span><span class="sxs-lookup"><span data-stu-id="297f0-112">As a result, it displays the returned collection (based on the `myTaskTemplate`<xref:System.Windows.DataTemplate>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="297f0-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="297f0-113">See Also</span></span>  
 [<span data-ttu-id="297f0-114">Hacer que los datos estén disponibles para el enlace en XAML</span><span class="sxs-lookup"><span data-stu-id="297f0-114">Make Data Available for Binding in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)  
 [<span data-ttu-id="297f0-115">Enlazar a una colección y mostrar información basada en la selección</span><span class="sxs-lookup"><span data-stu-id="297f0-115">Bind to a Collection and Display Information Based on Selection</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)  
 [<span data-ttu-id="297f0-116">Novedades de WPF versión 4.5</span><span class="sxs-lookup"><span data-stu-id="297f0-116">What's New in WPF Version 4.5</span></span>](../../../../docs/framework/wpf/getting-started/whats-new.md)  
 [<span data-ttu-id="297f0-117">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="297f0-117">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="297f0-118">Temas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="297f0-118">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
