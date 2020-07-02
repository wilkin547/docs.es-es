---
title: 'Cómo: Enlazar a una colección y mostrar información basada en la selección'
description: Siga este ejemplo para averiguar cómo enlazar a una colección y Mostrar información basada en la selección en el Windows Presentation Foundation (WPF).
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
ms.openlocfilehash: fb8757ee6818a2812308a0a132fa9d06951ad52e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619616"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a><span data-ttu-id="60037-103">Cómo: Enlazar a una colección y mostrar información basada en la selección</span><span class="sxs-lookup"><span data-stu-id="60037-103">How to: Bind to a Collection and Display Information Based on Selection</span></span>
<span data-ttu-id="60037-104">En un escenario simple de detalles maestros, tiene un enlace de datos <xref:System.Windows.Controls.ItemsControl> como <xref:System.Windows.Controls.ListBox> .</span><span class="sxs-lookup"><span data-stu-id="60037-104">In a simple master-detail scenario, you have a data-bound <xref:System.Windows.Controls.ItemsControl> such as a <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="60037-105">En función de la selección del usuario, se muestra más información sobre el elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="60037-105">Based on user selection, you display more information about the selected item.</span></span> <span data-ttu-id="60037-106">En este ejemplo se muestra cómo implementar este escenario.</span><span class="sxs-lookup"><span data-stu-id="60037-106">This example shows how to implement this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60037-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="60037-107">Example</span></span>  
 <span data-ttu-id="60037-108">En este ejemplo, `People` es una <xref:System.Collections.ObjectModel.ObservableCollection%601> de `Person` las clases de.</span><span class="sxs-lookup"><span data-stu-id="60037-108">In this example, `People` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `Person` classes.</span></span> <span data-ttu-id="60037-109">Esta `Person` clase contiene tres propiedades: `FirstName` , `LastName` y `HomeTown` , todas de tipo `string` .</span><span class="sxs-lookup"><span data-stu-id="60037-109">This `Person` class contains three properties: `FirstName`, `LastName`, and `HomeTown`, all of type `string`.</span></span>  
  
 [!code-xaml[CollectionBinding#Source](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="60037-110"><xref:System.Windows.Controls.ContentControl>Utiliza lo siguiente <xref:System.Windows.DataTemplate> que define cómo se presenta la información de un `Person` :</span><span class="sxs-lookup"><span data-stu-id="60037-110">The <xref:System.Windows.Controls.ContentControl> uses the following <xref:System.Windows.DataTemplate> that defines how the information of a `Person` is presented:</span></span>  
  
 [!code-xaml[CollectionBinding#DetailTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 <span data-ttu-id="60037-111">A continuación se muestra una captura de pantalla de lo que produce el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="60037-111">The following is a screenshot of what the example produces.</span></span> <span data-ttu-id="60037-112"><xref:System.Windows.Controls.ContentControl>Muestra las otras propiedades de la persona seleccionada.</span><span class="sxs-lookup"><span data-stu-id="60037-112">The <xref:System.Windows.Controls.ContentControl> shows the other properties of the person selected.</span></span>  
  
 <span data-ttu-id="60037-113">![Enlace a una colección](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span><span class="sxs-lookup"><span data-stu-id="60037-113">![Binding to a collection](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span></span>  
  
 <span data-ttu-id="60037-114">Los dos aspectos que se deben tener en cuenta en este ejemplo son:</span><span class="sxs-lookup"><span data-stu-id="60037-114">The two things to notice in this example are:</span></span>  
  
1. <span data-ttu-id="60037-115"><xref:System.Windows.Controls.ListBox>Y <xref:System.Windows.Controls.ContentControl> enlazan al mismo origen.</span><span class="sxs-lookup"><span data-stu-id="60037-115">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.ContentControl> bind to the same source.</span></span> <span data-ttu-id="60037-116"><xref:System.Windows.Data.Binding.Path%2A>No se especifican las propiedades de ambos enlaces porque ambos controles se enlazan a todo el objeto de colección.</span><span class="sxs-lookup"><span data-stu-id="60037-116">The <xref:System.Windows.Data.Binding.Path%2A> properties of both bindings are not specified because both controls are binding to the entire collection object.</span></span>  
  
2. <span data-ttu-id="60037-117">Debe establecer la <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> propiedad en `true` para que funcione.</span><span class="sxs-lookup"><span data-stu-id="60037-117">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` for this to work.</span></span> <span data-ttu-id="60037-118">Al establecer esta propiedad, se asegura de que el elemento seleccionado siempre se establece como <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A> .</span><span class="sxs-lookup"><span data-stu-id="60037-118">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="60037-119">Como alternativa, si <xref:System.Windows.Controls.ListBox> obtiene datos de una <xref:System.Windows.Data.CollectionViewSource> , sincroniza la selección y la moneda automáticamente.</span><span class="sxs-lookup"><span data-stu-id="60037-119">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="60037-120">Tenga en cuenta que la `Person` clase invalida el `ToString` método de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="60037-120">Note that the `Person` class overrides the `ToString` method the following way.</span></span> <span data-ttu-id="60037-121">De forma predeterminada, <xref:System.Windows.Controls.ListBox> llama a `ToString` y muestra una representación de cadena de cada objeto de la colección enlazada.</span><span class="sxs-lookup"><span data-stu-id="60037-121">By default, the <xref:System.Windows.Controls.ListBox> calls `ToString` and displays a string representation of each object in the bound collection.</span></span> <span data-ttu-id="60037-122">Esa es la razón por la que cada `Person` aparece como un nombre en el <xref:System.Windows.Controls.ListBox> .</span><span class="sxs-lookup"><span data-stu-id="60037-122">That is why each `Person` appears as a first name in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-csharp[CollectionBinding#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a><span data-ttu-id="60037-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="60037-123">See also</span></span>

- [<span data-ttu-id="60037-124">Usar el patrón principal-detalle con datos jerárquicos</span><span class="sxs-lookup"><span data-stu-id="60037-124">Use the Master-Detail Pattern with Hierarchical Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [<span data-ttu-id="60037-125">Usar el patrón principal-detalle con datos XML jerárquicos</span><span class="sxs-lookup"><span data-stu-id="60037-125">Use the Master-Detail Pattern with Hierarchical XML Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [<span data-ttu-id="60037-126">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="60037-126">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="60037-127">Información general sobre plantillas de datos</span><span class="sxs-lookup"><span data-stu-id="60037-127">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="60037-128">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="60037-128">How-to Topics</span></span>](data-binding-how-to-topics.md)
