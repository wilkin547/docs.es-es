---
title: "Cómo: Usar el patrón principal-detalle con datos jerárquicos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2e392b47682d1bf53dc31073920bdf212fb7d997
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a><span data-ttu-id="da601-102">Cómo: Usar el patrón principal-detalle con datos jerárquicos</span><span class="sxs-lookup"><span data-stu-id="da601-102">How to: Use the Master-Detail Pattern with Hierarchical Data</span></span>
<span data-ttu-id="da601-103">En este ejemplo se muestra cómo implementar el escenario principal-detalle.</span><span class="sxs-lookup"><span data-stu-id="da601-103">This example shows how to implement the master-detail scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da601-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="da601-104">Example</span></span>  
 <span data-ttu-id="da601-105">En este ejemplo, `LeagueList` es una colección de `Leagues`.</span><span class="sxs-lookup"><span data-stu-id="da601-105">In this example, `LeagueList` is a collection of `Leagues`.</span></span> <span data-ttu-id="da601-106">Cada `League` tiene un `Name` y una colección de `Divisions`y cada `Division` tiene un nombre y una colección de `Teams`.</span><span class="sxs-lookup"><span data-stu-id="da601-106">Each `League` has a `Name` and a collection of `Divisions`, and each `Division` has a name and a collection of `Teams`.</span></span> <span data-ttu-id="da601-107">Cada `Team` tiene un nombre de equipo.</span><span class="sxs-lookup"><span data-stu-id="da601-107">Each `Team` has a team name.</span></span>  
  
 [!code-xaml[MasterDetail#HowTo1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 <span data-ttu-id="da601-108">La siguiente captura de pantalla muestra el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="da601-108">The following is a screenshot of the example.</span></span> <span data-ttu-id="da601-109">El `Divisions` <xref:System.Windows.Controls.ListBox> automáticamente realiza un seguimiento de las selecciones en la `Leagues` <xref:System.Windows.Controls.ListBox> y mostrar los datos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="da601-109">The `Divisions` <xref:System.Windows.Controls.ListBox> automatically tracks selections in the `Leagues` <xref:System.Windows.Controls.ListBox> and display the corresponding data.</span></span> <span data-ttu-id="da601-110">El `Teams` <xref:System.Windows.Controls.ListBox> realiza un seguimiento de las selecciones en los otros dos <xref:System.Windows.Controls.ListBox> controles.</span><span class="sxs-lookup"><span data-stu-id="da601-110">The `Teams` <xref:System.Windows.Controls.ListBox> tracks selections in the other two <xref:System.Windows.Controls.ListBox> controls.</span></span>  
  
 <span data-ttu-id="da601-111">![Patrón &#45; ejemplo detalle](../../../../docs/framework/wpf/data/media/databindingmasterdetailsample.png "DataBindingMasterDetailSample")</span><span class="sxs-lookup"><span data-stu-id="da601-111">![Master&#45;detail example](../../../../docs/framework/wpf/data/media/databindingmasterdetailsample.png "DataBindingMasterDetailSample")</span></span>  
  
 <span data-ttu-id="da601-112">Las dos cosas que se observan en este ejemplo son:</span><span class="sxs-lookup"><span data-stu-id="da601-112">The two things to notice in this example are:</span></span>  
  
1.  <span data-ttu-id="da601-113">Los tres <xref:System.Windows.Controls.ListBox> controles se enlazan al mismo origen.</span><span class="sxs-lookup"><span data-stu-id="da601-113">The three <xref:System.Windows.Controls.ListBox> controls bind to the same source.</span></span> <span data-ttu-id="da601-114">Establece el <xref:System.Windows.Data.Binding.Path%2A> propiedad del enlace para especificar el nivel de datos desea que el <xref:System.Windows.Controls.ListBox> para mostrar.</span><span class="sxs-lookup"><span data-stu-id="da601-114">You set the <xref:System.Windows.Data.Binding.Path%2A> property of the binding to specify which level of data you want the <xref:System.Windows.Controls.ListBox> to display.</span></span>  
  
2.  <span data-ttu-id="da601-115">Debe establecer el <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> propiedad `true` en el <xref:System.Windows.Controls.ListBox> controles de los cuales la selección está realizando el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="da601-115">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` on the <xref:System.Windows.Controls.ListBox> controls of which the selection you are tracking.</span></span> <span data-ttu-id="da601-116">Al establecer esta propiedad se asegura de que el elemento seleccionado siempre se establece como el <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="da601-116">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="da601-117">Como alternativa, si la <xref:System.Windows.Controls.ListBox> obtiene datos de un <xref:System.Windows.Data.CollectionViewSource>, sincroniza automáticamente selección y moneda.</span><span class="sxs-lookup"><span data-stu-id="da601-117">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="da601-118">La técnica es ligeramente diferente cuando se utiliza [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos.</span><span class="sxs-lookup"><span data-stu-id="da601-118">The technique is slightly different when you are using [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span> <span data-ttu-id="da601-119">Para obtener un ejemplo, vea [usar el patrón principal-detalle con datos XML jerárquicos](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="da601-119">For an example, see [Use the Master-Detail Pattern with Hierarchical XML Data](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da601-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="da601-120">See Also</span></span>  
 <xref:System.Windows.HierarchicalDataTemplate>  
 [<span data-ttu-id="da601-121">Enlazar a una colección y mostrar información basada en la selección</span><span class="sxs-lookup"><span data-stu-id="da601-121">Bind to a Collection and Display Information Based on Selection</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)  
 [<span data-ttu-id="da601-122">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="da601-122">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="da601-123">Información general sobre plantillas de datos</span><span class="sxs-lookup"><span data-stu-id="da601-123">Data Templating Overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [<span data-ttu-id="da601-124">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="da601-124">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
