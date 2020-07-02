---
title: 'Cómo: Ordenar y agrupar datos mediante una vista en XAML'
description: Obtenga información sobre cómo crear una vista de una recopilación de datos para agrupar, ordenar y filtrar en el Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], grouping data in views in XAML
- XAML [WPF], sorting data in views
- grouping data in views in XAML [WPF]
- data binding [WPF], sorting data in views in XAML
- sorting data in views in XAML [WPF]
- XAML [WPF], grouping data in views
- views [WPF], sorting data
- views [WPF], grouping data
ms.assetid: 145c8c3f-dbdd-4d0d-816f-90b35eba7eda
ms.openlocfilehash: a4f8e2de9345dba8e4ea0d3a16a32d57a9adb55c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621683"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a><span data-ttu-id="ce9f2-103">Cómo: Ordenar y agrupar datos mediante una vista en XAML</span><span class="sxs-lookup"><span data-stu-id="ce9f2-103">How to: Sort and Group Data Using a View in XAML</span></span>
<span data-ttu-id="ce9f2-104">En este ejemplo se muestra cómo crear una vista de una recopilación de datos en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ce9f2-104">This example shows how to create a view of a data collection in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="ce9f2-105">Las vistas permiten la funcionalidad de agrupación, ordenación, filtrado y noción de un elemento actual.</span><span class="sxs-lookup"><span data-stu-id="ce9f2-105">Views allow for the functionalities of grouping, sorting, filtering, and the notion of a current item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce9f2-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ce9f2-106">Example</span></span>  
 <span data-ttu-id="ce9f2-107">En el ejemplo siguiente, el recurso estático denominado *lugares* se define como una colección de objetos *Place* , en la que *cada uno de* los objetos se compone de un nombre de ciudad y el estado.</span><span class="sxs-lookup"><span data-stu-id="ce9f2-107">In the following example, the static resource named *places* is defined as a collection of *Place* objects, in which each *Place* object is consisted of a city name and the state.</span></span> <span data-ttu-id="ce9f2-108">El prefijo *src* se asigna al espacio de nombres donde se definen los *lugares* de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="ce9f2-108">The prefix *src* is mapped to the namespace where the data source *Places* is defined.</span></span> <span data-ttu-id="ce9f2-109">El prefijo *SCM* se asigna a `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` y los *DAT* se asignan a `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"` .</span><span class="sxs-lookup"><span data-stu-id="ce9f2-109">The prefix *scm* maps to `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` and *dat* maps to `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.</span></span>  
  
 <span data-ttu-id="ce9f2-110">En el ejemplo siguiente se crea una vista de la recopilación de datos que se ordena por el nombre de la ciudad y se agrupa por el estado.</span><span class="sxs-lookup"><span data-stu-id="ce9f2-110">The following example creates a view of the data collection that is sorted by the city name and grouped by the state.</span></span>  
  
 [!code-xaml[CollectionViewSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 <span data-ttu-id="ce9f2-111">A continuación, la vista puede ser un origen de enlace, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ce9f2-111">The view can then be a binding source, as in the following example:</span></span>  
  
 [!code-xaml[CollectionViewSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 <span data-ttu-id="ce9f2-112">Para los enlaces a los datos XML definidos en un <xref:System.Windows.Data.XmlDataProvider> recurso, debe anteponer un símbolo @ al nombre XML.</span><span class="sxs-lookup"><span data-stu-id="ce9f2-112">For bindings to XML data defined in an <xref:System.Windows.Data.XmlDataProvider> resource, precede the XML name with an @ symbol.</span></span>  
  
 [!code-xaml[CollectionViewSource#XDPChunk](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a><span data-ttu-id="ce9f2-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce9f2-113">See also</span></span>

- <xref:System.Windows.Data.CollectionViewSource>
- [<span data-ttu-id="ce9f2-114">Obtener la vista predeterminada de una recopilación de datos</span><span class="sxs-lookup"><span data-stu-id="ce9f2-114">Get the Default View of a Data Collection</span></span>](how-to-get-the-default-view-of-a-data-collection.md)
- [<span data-ttu-id="ce9f2-115">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="ce9f2-115">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="ce9f2-116">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="ce9f2-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
