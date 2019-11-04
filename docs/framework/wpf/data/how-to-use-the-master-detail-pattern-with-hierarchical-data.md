---
title: 'Cómo: Usar el patrón principal-detalle con datos jerárquicos'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
ms.openlocfilehash: 2e7d9ceed3ab8385f07d87ecdb92c0a99d410b40
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459079"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a><span data-ttu-id="67410-102">Cómo: Usar el patrón principal-detalle con datos jerárquicos</span><span class="sxs-lookup"><span data-stu-id="67410-102">How to: Use the Master-Detail Pattern with Hierarchical Data</span></span>
<span data-ttu-id="67410-103">Este ejemplo muestra cómo implementar el escenario principal-detalle.</span><span class="sxs-lookup"><span data-stu-id="67410-103">This example shows how to implement the master-detail scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67410-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67410-104">Example</span></span>  
 <span data-ttu-id="67410-105">En este ejemplo, `LeagueList` es una colección de `Leagues`.</span><span class="sxs-lookup"><span data-stu-id="67410-105">In this example, `LeagueList` is a collection of `Leagues`.</span></span> <span data-ttu-id="67410-106">Cada `League` tiene una `Name` y una colección de `Divisions`, y cada `Division` tiene un nombre y una colección de `Teams`.</span><span class="sxs-lookup"><span data-stu-id="67410-106">Each `League` has a `Name` and a collection of `Divisions`, and each `Division` has a name and a collection of `Teams`.</span></span> <span data-ttu-id="67410-107">Cada `Team` tiene un nombre de equipo.</span><span class="sxs-lookup"><span data-stu-id="67410-107">Each `Team` has a team name.</span></span>  
  
 [!code-xaml[MasterDetail#HowTo1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 <span data-ttu-id="67410-108">La siguiente captura de pantalla muestra el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="67410-108">The following is a screenshot of the example.</span></span> <span data-ttu-id="67410-109">El `Divisions` <xref:System.Windows.Controls.ListBox> realiza un seguimiento automático de las selecciones en el `Leagues` <xref:System.Windows.Controls.ListBox> y muestra los datos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="67410-109">The `Divisions` <xref:System.Windows.Controls.ListBox> automatically tracks selections in the `Leagues` <xref:System.Windows.Controls.ListBox> and display the corresponding data.</span></span> <span data-ttu-id="67410-110">El `Teams` <xref:System.Windows.Controls.ListBox> realiza un seguimiento de las selecciones en los otros dos controles de <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="67410-110">The `Teams` <xref:System.Windows.Controls.ListBox> tracks selections in the other two <xref:System.Windows.Controls.ListBox> controls.</span></span>  
  
 ![Captura de pantalla que muestra&#45;un ejemplo de escenario de detalle maestro.](./media/how-to-use-the-master-detail-pattern-with-hierarchical-data/databinding-master-detail-scenario.png)  
  
 <span data-ttu-id="67410-112">Los dos aspectos que se deben tener en cuenta en este ejemplo son:</span><span class="sxs-lookup"><span data-stu-id="67410-112">The two things to notice in this example are:</span></span>  
  
1. <span data-ttu-id="67410-113">Los tres controles <xref:System.Windows.Controls.ListBox> enlazan al mismo origen.</span><span class="sxs-lookup"><span data-stu-id="67410-113">The three <xref:System.Windows.Controls.ListBox> controls bind to the same source.</span></span> <span data-ttu-id="67410-114">Establezca la propiedad <xref:System.Windows.Data.Binding.Path%2A> del enlace para especificar el nivel de datos que desea que muestre el <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="67410-114">You set the <xref:System.Windows.Data.Binding.Path%2A> property of the binding to specify which level of data you want the <xref:System.Windows.Controls.ListBox> to display.</span></span>  
  
2. <span data-ttu-id="67410-115">Debe establecer la propiedad <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> en `true` en los controles de <xref:System.Windows.Controls.ListBox> de los que se realiza el seguimiento de la selección.</span><span class="sxs-lookup"><span data-stu-id="67410-115">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` on the <xref:System.Windows.Controls.ListBox> controls of which the selection you are tracking.</span></span> <span data-ttu-id="67410-116">Al establecer esta propiedad, se asegura de que el elemento seleccionado siempre se establece como <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="67410-116">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="67410-117">Como alternativa, si el <xref:System.Windows.Controls.ListBox> obtiene datos de una <xref:System.Windows.Data.CollectionViewSource>, sincroniza la selección y la moneda automáticamente.</span><span class="sxs-lookup"><span data-stu-id="67410-117">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="67410-118">La técnica es ligeramente diferente cuando se usan datos de [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67410-118">The technique is slightly different when you are using [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span> <span data-ttu-id="67410-119">Para obtener un ejemplo, consulte [usar el patrón principal-detalle con datos XML jerárquicos](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="67410-119">For an example, see [Use the Master-Detail Pattern with Hierarchical XML Data](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67410-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="67410-120">See also</span></span>

- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="67410-121">Enlazar a una colección y mostrar información basada en la selección</span><span class="sxs-lookup"><span data-stu-id="67410-121">Bind to a Collection and Display Information Based on Selection</span></span>](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [<span data-ttu-id="67410-122">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="67410-122">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="67410-123">Información general sobre plantillas de datos</span><span class="sxs-lookup"><span data-stu-id="67410-123">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="67410-124">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="67410-124">How-to Topics</span></span>](data-binding-how-to-topics.md)
