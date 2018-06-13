---
title: 'Cómo: Enlazar a una colección y mostrar información basada en la selección'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], selecting data for views
- data binding [WPF], creating views of data collections
- data binding [WPF], selecting data for views
- data binding [WPF], binding to collections
ms.assetid: 952a7d76-dd29-49e5-86f5-32c4530e70eb
ms.openlocfilehash: 154f4b9b6024d064e73d64c44e2398a5da47052c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557416"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a><span data-ttu-id="3bd32-102">Cómo: Enlazar a una colección y mostrar información basada en la selección</span><span class="sxs-lookup"><span data-stu-id="3bd32-102">How to: Bind to a Collection and Display Information Based on Selection</span></span>
<span data-ttu-id="3bd32-103">En un escenario principal-detalle simple, tiene un enlace de datos <xref:System.Windows.Controls.ItemsControl> como un <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="3bd32-103">In a simple master-detail scenario, you have a data-bound <xref:System.Windows.Controls.ItemsControl> such as a <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="3bd32-104">En función de la selección del usuario, se muestra más información acerca del elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3bd32-104">Based on user selection, you display more information about the selected item.</span></span> <span data-ttu-id="3bd32-105">Este ejemplo muestra cómo implementar este escenario.</span><span class="sxs-lookup"><span data-stu-id="3bd32-105">This example shows how to implement this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bd32-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3bd32-106">Example</span></span>  
 <span data-ttu-id="3bd32-107">En este ejemplo, `People` es un <xref:System.Collections.ObjectModel.ObservableCollection%601> de `Person` clases.</span><span class="sxs-lookup"><span data-stu-id="3bd32-107">In this example, `People` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `Person` classes.</span></span> <span data-ttu-id="3bd32-108">Esto `Person` clase contiene tres propiedades: `FirstName`, `LastName`, y `HomeTown`, todos del tipo `string`.</span><span class="sxs-lookup"><span data-stu-id="3bd32-108">This `Person` class contains three properties: `FirstName`, `LastName`, and `HomeTown`, all of type `string`.</span></span>  
  
 [!code-xaml[CollectionBinding#Source](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="3bd32-109">El <xref:System.Windows.Controls.ContentControl> usa las siguientes <xref:System.Windows.DataTemplate> que define cómo la información de un `Person` se presenta:</span><span class="sxs-lookup"><span data-stu-id="3bd32-109">The <xref:System.Windows.Controls.ContentControl> uses the following <xref:System.Windows.DataTemplate> that defines how the information of a `Person` is presented:</span></span>  
  
 [!code-xaml[CollectionBinding#DetailTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 <span data-ttu-id="3bd32-110">La siguiente es una captura de pantalla de lo que genera el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3bd32-110">The following is a screenshot of what the example produces.</span></span> <span data-ttu-id="3bd32-111">La <xref:System.Windows.Controls.ContentControl> muestra las demás propiedades de la persona seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3bd32-111">The <xref:System.Windows.Controls.ContentControl> shows the other properties of the person selected.</span></span>  
  
 <span data-ttu-id="3bd32-112">![Enlazar a una colección](../../../../docs/framework/wpf/data/media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span><span class="sxs-lookup"><span data-stu-id="3bd32-112">![Binding to a collection](../../../../docs/framework/wpf/data/media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span></span>  
  
 <span data-ttu-id="3bd32-113">Las dos cosas que se observan en este ejemplo son:</span><span class="sxs-lookup"><span data-stu-id="3bd32-113">The two things to notice in this example are:</span></span>  
  
1.  <span data-ttu-id="3bd32-114">El <xref:System.Windows.Controls.ListBox> y <xref:System.Windows.Controls.ContentControl> enlazar al mismo origen.</span><span class="sxs-lookup"><span data-stu-id="3bd32-114">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.ContentControl> bind to the same source.</span></span> <span data-ttu-id="3bd32-115">El <xref:System.Windows.Data.Binding.Path%2A> no se especificaron las propiedades de ambos enlaces porque ambos controles se enlazan con el objeto de colección completa.</span><span class="sxs-lookup"><span data-stu-id="3bd32-115">The <xref:System.Windows.Data.Binding.Path%2A> properties of both bindings are not specified because both controls are binding to the entire collection object.</span></span>  
  
2.  <span data-ttu-id="3bd32-116">Debe establecer el <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> propiedad `true` para que funcione.</span><span class="sxs-lookup"><span data-stu-id="3bd32-116">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` for this to work.</span></span> <span data-ttu-id="3bd32-117">Al establecer esta propiedad se asegura de que el elemento seleccionado siempre se establece como el <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="3bd32-117">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="3bd32-118">Como alternativa, si la <xref:System.Windows.Controls.ListBox> obtiene datos de un <xref:System.Windows.Data.CollectionViewSource>, sincroniza automáticamente selección y moneda.</span><span class="sxs-lookup"><span data-stu-id="3bd32-118">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="3bd32-119">Tenga en cuenta que la `Person` clase invalida la `ToString` método del siguiente modo.</span><span class="sxs-lookup"><span data-stu-id="3bd32-119">Note that the `Person` class overrides the `ToString` method the following way.</span></span> <span data-ttu-id="3bd32-120">De forma predeterminada, el <xref:System.Windows.Controls.ListBox> llamadas `ToString` y muestra una representación de cadena de cada objeto en la colección enlazada.</span><span class="sxs-lookup"><span data-stu-id="3bd32-120">By default, the <xref:System.Windows.Controls.ListBox> calls `ToString` and displays a string representation of each object in the bound collection.</span></span> <span data-ttu-id="3bd32-121">Por eso cada `Person` aparece como un nombre en el <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="3bd32-121">That is why each `Person` appears as a first name in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-csharp[CollectionBinding#ToString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a><span data-ttu-id="3bd32-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="3bd32-122">See Also</span></span>  
 [<span data-ttu-id="3bd32-123">Usar el patrón principal-detalle con datos jerárquicos</span><span class="sxs-lookup"><span data-stu-id="3bd32-123">Use the Master-Detail Pattern with Hierarchical Data</span></span>](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)  
 [<span data-ttu-id="3bd32-124">Usar el patrón principal-detalle con datos XML jerárquicos</span><span class="sxs-lookup"><span data-stu-id="3bd32-124">Use the Master-Detail Pattern with Hierarchical XML Data</span></span>](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)  
 [<span data-ttu-id="3bd32-125">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="3bd32-125">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="3bd32-126">Información general sobre plantillas de datos</span><span class="sxs-lookup"><span data-stu-id="3bd32-126">Data Templating Overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [<span data-ttu-id="3bd32-127">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="3bd32-127">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
