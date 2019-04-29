---
title: Procedimiento Usar el patrón maestro y detalle con datos jerárquicos
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
ms.openlocfilehash: e0bbb24b07fdc1c362e2be43d69d189defbc27a4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61931902"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a><span data-ttu-id="33dd2-102">Procedimiento Usar el patrón maestro y detalle con datos jerárquicos</span><span class="sxs-lookup"><span data-stu-id="33dd2-102">How to: Use the Master-Detail Pattern with Hierarchical Data</span></span>
<span data-ttu-id="33dd2-103">En este ejemplo se muestra cómo implementar el escenario principal-detalle.</span><span class="sxs-lookup"><span data-stu-id="33dd2-103">This example shows how to implement the master-detail scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33dd2-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="33dd2-104">Example</span></span>  
 <span data-ttu-id="33dd2-105">En este ejemplo, `LeagueList` es una colección de `Leagues`.</span><span class="sxs-lookup"><span data-stu-id="33dd2-105">In this example, `LeagueList` is a collection of `Leagues`.</span></span> <span data-ttu-id="33dd2-106">Cada `League` tiene un `Name` y una colección de `Divisions`y cada `Division` tiene un nombre y una colección de `Teams`.</span><span class="sxs-lookup"><span data-stu-id="33dd2-106">Each `League` has a `Name` and a collection of `Divisions`, and each `Division` has a name and a collection of `Teams`.</span></span> <span data-ttu-id="33dd2-107">Cada `Team` tiene un nombre de equipo.</span><span class="sxs-lookup"><span data-stu-id="33dd2-107">Each `Team` has a team name.</span></span>  
  
 [!code-xaml[MasterDetail#HowTo1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 <span data-ttu-id="33dd2-108">La siguiente captura de pantalla muestra el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="33dd2-108">The following is a screenshot of the example.</span></span> <span data-ttu-id="33dd2-109">El `Divisions` <xref:System.Windows.Controls.ListBox> automáticamente realiza un seguimiento de las selecciones en la `Leagues` <xref:System.Windows.Controls.ListBox> y mostrar los datos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="33dd2-109">The `Divisions` <xref:System.Windows.Controls.ListBox> automatically tracks selections in the `Leagues` <xref:System.Windows.Controls.ListBox> and display the corresponding data.</span></span> <span data-ttu-id="33dd2-110">El `Teams` <xref:System.Windows.Controls.ListBox> realiza un seguimiento de las selecciones en las otras dos <xref:System.Windows.Controls.ListBox> controles.</span><span class="sxs-lookup"><span data-stu-id="33dd2-110">The `Teams` <xref:System.Windows.Controls.ListBox> tracks selections in the other two <xref:System.Windows.Controls.ListBox> controls.</span></span>  
  
 ![Captura de pantalla que muestra un patrón&#45;ejemplo de escenario de detalle.](./media/how-to-use-the-master-detail-pattern-with-hierarchical-data/databinding-master-detail-scenario.png)  
  
 <span data-ttu-id="33dd2-112">Las dos cosas a tener en cuenta en este ejemplo son:</span><span class="sxs-lookup"><span data-stu-id="33dd2-112">The two things to notice in this example are:</span></span>  
  
1. <span data-ttu-id="33dd2-113">Los tres <xref:System.Windows.Controls.ListBox> los controles se enlazan al mismo origen.</span><span class="sxs-lookup"><span data-stu-id="33dd2-113">The three <xref:System.Windows.Controls.ListBox> controls bind to the same source.</span></span> <span data-ttu-id="33dd2-114">Establece el <xref:System.Windows.Data.Binding.Path%2A> propiedad del enlace para especificar el nivel de datos desea que el <xref:System.Windows.Controls.ListBox> para mostrar.</span><span class="sxs-lookup"><span data-stu-id="33dd2-114">You set the <xref:System.Windows.Data.Binding.Path%2A> property of the binding to specify which level of data you want the <xref:System.Windows.Controls.ListBox> to display.</span></span>  
  
2. <span data-ttu-id="33dd2-115">Debe establecer el <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> propiedad `true` en el <xref:System.Windows.Controls.ListBox> controles de los cuales la selección está realizando el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="33dd2-115">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` on the <xref:System.Windows.Controls.ListBox> controls of which the selection you are tracking.</span></span> <span data-ttu-id="33dd2-116">Al establecer esta propiedad garantiza que siempre se establece el elemento seleccionado como el <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="33dd2-116">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="33dd2-117">Como alternativa, si la <xref:System.Windows.Controls.ListBox> obtiene sus datos desde un <xref:System.Windows.Data.CollectionViewSource>, sincronización automáticamente selección y moneda.</span><span class="sxs-lookup"><span data-stu-id="33dd2-117">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="33dd2-118">La técnica es ligeramente diferente cuando se usa [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos.</span><span class="sxs-lookup"><span data-stu-id="33dd2-118">The technique is slightly different when you are using [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span> <span data-ttu-id="33dd2-119">Para obtener un ejemplo, vea [usar el patrón principal-detalle con datos XML jerárquicos](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="33dd2-119">For an example, see [Use the Master-Detail Pattern with Hierarchical XML Data](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33dd2-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="33dd2-120">See also</span></span>

- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="33dd2-121">Enlazar a una colección y mostrar información basada en la selección</span><span class="sxs-lookup"><span data-stu-id="33dd2-121">Bind to a Collection and Display Information Based on Selection</span></span>](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [<span data-ttu-id="33dd2-122">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="33dd2-122">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="33dd2-123">Información general sobre plantillas de datos</span><span class="sxs-lookup"><span data-stu-id="33dd2-123">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="33dd2-124">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="33dd2-124">How-to Topics</span></span>](data-binding-how-to-topics.md)
