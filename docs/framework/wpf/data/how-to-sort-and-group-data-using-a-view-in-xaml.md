---
title: 'Cómo: Ordenar y agrupar datos mediante una vista en XAML'
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
ms.openlocfilehash: 80529420bcc5fdca473313e164b3d096732953f4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555835"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a><span data-ttu-id="ddcde-102">Cómo: Ordenar y agrupar datos mediante una vista en XAML</span><span class="sxs-lookup"><span data-stu-id="ddcde-102">How to: Sort and Group Data Using a View in XAML</span></span>
<span data-ttu-id="ddcde-103">Este ejemplo muestra cómo crear una vista de una recolección de datos en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ddcde-103">This example shows how to create a view of a data collection in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="ddcde-104">Las vistas permiten para las funciones de agrupación, ordenación, filtrado y la noción de un elemento actual.</span><span class="sxs-lookup"><span data-stu-id="ddcde-104">Views allow for the functionalities of grouping, sorting, filtering, and the notion of a current item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddcde-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ddcde-105">Example</span></span>  
 <span data-ttu-id="ddcde-106">En el ejemplo siguiente, el recurso estático denominado *coloca* se define como una colección de *lugar* objetos, donde cada *lugar* objeto consta de un nombre de ciudad y el estado.</span><span class="sxs-lookup"><span data-stu-id="ddcde-106">In the following example, the static resource named *places* is defined as a collection of *Place* objects, in which each *Place* object is consisted of a city name and the state.</span></span> <span data-ttu-id="ddcde-107">El prefijo *src* se asigna al espacio de nombres donde el origen de datos *lugares* está definido.</span><span class="sxs-lookup"><span data-stu-id="ddcde-107">The prefix *src* is mapped to the namespace where the data source *Places* is defined.</span></span> <span data-ttu-id="ddcde-108">El prefijo *scm* se asigna a `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` y *dat* se asigna a `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.</span><span class="sxs-lookup"><span data-stu-id="ddcde-108">The prefix *scm* maps to `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` and *dat* maps to `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.</span></span>  
  
 <span data-ttu-id="ddcde-109">En el ejemplo siguiente se crea una vista de la recopilación de datos que está ordenada por el nombre de la ciudad y agrupada por el estado.</span><span class="sxs-lookup"><span data-stu-id="ddcde-109">The following example creates a view of the data collection that is sorted by the city name and grouped by the state.</span></span>  
  
 [!code-xaml[CollectionViewSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 <span data-ttu-id="ddcde-110">La vista, a continuación, puede ser un origen de enlace, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ddcde-110">The view can then be a binding source, as in the following example:</span></span>  
  
 [!code-xaml[CollectionViewSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 <span data-ttu-id="ddcde-111">Para los enlaces a datos XML definidos en un <xref:System.Windows.Data.XmlDataProvider> recursos, incluya delante del nombre XML con un símbolo @.</span><span class="sxs-lookup"><span data-stu-id="ddcde-111">For bindings to XML data defined in an <xref:System.Windows.Data.XmlDataProvider> resource, precede the XML name with an @ symbol.</span></span>  
  
 [!code-xaml[CollectionViewSource#XDPChunk](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a><span data-ttu-id="ddcde-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="ddcde-112">See Also</span></span>  
 <xref:System.Windows.Data.CollectionViewSource>  
 [<span data-ttu-id="ddcde-113">Obtener la vista predeterminada de una colección de datos</span><span class="sxs-lookup"><span data-stu-id="ddcde-113">Get the Default View of a Data Collection</span></span>](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)  
 [<span data-ttu-id="ddcde-114">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="ddcde-114">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="ddcde-115">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="ddcde-115">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
