---
title: "Cómo: Implementar PriorityBinding"
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
helpviewer_keywords: data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9753462908928eaf177e100a16186826bf4828ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-prioritybinding"></a><span data-ttu-id="5759f-102">Cómo: Implementar PriorityBinding</span><span class="sxs-lookup"><span data-stu-id="5759f-102">How to: Implement PriorityBinding</span></span>
<span data-ttu-id="5759f-103"><xref:System.Windows.Data.PriorityBinding>en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] funciona mediante la especificación de una lista de enlaces.</span><span class="sxs-lookup"><span data-stu-id="5759f-103"><xref:System.Windows.Data.PriorityBinding> in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] works by specifying a list of bindings.</span></span> <span data-ttu-id="5759f-104">Se ordena la lista de enlaces de prioridad más alta a prioridad más baja.</span><span class="sxs-lookup"><span data-stu-id="5759f-104">The list of bindings is ordered from highest priority to lowest priority.</span></span> <span data-ttu-id="5759f-105">Si el enlace de máxima prioridad devuelve un valor correctamente cuando se procesa, a continuación, nunca hay una necesidad de procesar el resto de los enlaces en la lista.</span><span class="sxs-lookup"><span data-stu-id="5759f-105">If the highest priority binding returns a value successfully when it is processed then there is never a need to process the other bindings in the list.</span></span> <span data-ttu-id="5759f-106">Podría ser el caso de que el enlace de máxima prioridad tarda mucho tiempo en evaluarse, se utilizará la siguiente prioridad más alta que devuelve un valor correctamente hasta que un enlace de una prioridad más alta devuelve un valor correctamente.</span><span class="sxs-lookup"><span data-stu-id="5759f-106">It could be the case that the highest priority binding takes a long time to be evaluated, the next highest priority that returns a value successfully will be used until a binding of a higher priority returns a value successfully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5759f-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5759f-107">Example</span></span>  
 <span data-ttu-id="5759f-108">Para demostrar cómo <xref:System.Windows.Data.PriorityBinding> funciona, el `AsyncDataSource` se ha creado el objeto con las tres propiedades siguientes: `FastDP`, `SlowerDP`, y `SlowestDP`.</span><span class="sxs-lookup"><span data-stu-id="5759f-108">To demonstrate how <xref:System.Windows.Data.PriorityBinding> works, the `AsyncDataSource` object has been created with the following three properties: `FastDP`, `SlowerDP`, and `SlowestDP`.</span></span>  
  
 <span data-ttu-id="5759f-109">El descriptor de acceso get de `FastDP` devuelve el valor de la `_fastDP` miembro de datos.</span><span class="sxs-lookup"><span data-stu-id="5759f-109">The get accessor of `FastDP` returns the value of the `_fastDP` data member.</span></span>  
  
 <span data-ttu-id="5759f-110">El descriptor de acceso get de `SlowerDP` espera durante 3 segundos antes de devolver el valor de la `_slowerDP` miembro de datos.</span><span class="sxs-lookup"><span data-stu-id="5759f-110">The get accessor of `SlowerDP` waits for 3 seconds before returning the value of the `_slowerDP` data member.</span></span>  
  
 <span data-ttu-id="5759f-111">El descriptor de acceso get de `SlowestDP` esperará 5 segundos antes de devolver el valor de la `_slowestDP` miembro de datos.</span><span class="sxs-lookup"><span data-stu-id="5759f-111">The get accessor of `SlowestDP` waits for 5 seconds before returning the value of the `_slowestDP` data member.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5759f-112">En este ejemplo es solo con fines de demostración.</span><span class="sxs-lookup"><span data-stu-id="5759f-112">This example is for demonstration purposes only.</span></span> <span data-ttu-id="5759f-113">El [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] directrices se recomiendan definir las propiedades que son órdenes de magnitud más lentas de lo que sería un conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="5759f-113">The [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] guidelines recommend against defining properties that are orders of magnitude slower than a field set would be.</span></span> <span data-ttu-id="5759f-114">Para obtener más información, consulte [NIB: elegir entre propiedades y métodos](http://msdn.microsoft.com/en-us/55825e8f-7e2e-448a-9505-7217cc91b1af).</span><span class="sxs-lookup"><span data-stu-id="5759f-114">For more information, see [NIB: Choosing Between Properties and Methods](http://msdn.microsoft.com/en-us/55825e8f-7e2e-448a-9505-7217cc91b1af).</span></span>  
  
 [!code-csharp[PriorityBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 <span data-ttu-id="5759f-115">El <xref:System.Windows.Controls.TextBlock.Text%2A> propiedad se enlaza a los pasos anteriores `AsyncDS` con <xref:System.Windows.Data.PriorityBinding>:</span><span class="sxs-lookup"><span data-stu-id="5759f-115">The <xref:System.Windows.Controls.TextBlock.Text%2A> property binds to the above `AsyncDS` using <xref:System.Windows.Data.PriorityBinding>:</span></span>  
  
 [!code-xaml[PriorityBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="5759f-116">Cuando el motor de enlace procesa los <xref:System.Windows.Data.Binding> objetos, se inicia con la primera <xref:System.Windows.Data.Binding>, que está enlazado a la `SlowestDP` propiedad.</span><span class="sxs-lookup"><span data-stu-id="5759f-116">When the binding engine processes the <xref:System.Windows.Data.Binding> objects, it starts with the first <xref:System.Windows.Data.Binding>, which is bound to the `SlowestDP` property.</span></span> <span data-ttu-id="5759f-117">Cuando esto <xref:System.Windows.Data.Binding> está procesado, no devuelve un valor correctamente porque está inactivo durante 5 segundos, por lo que la próxima <xref:System.Windows.Data.Binding> se procesa el elemento.</span><span class="sxs-lookup"><span data-stu-id="5759f-117">When this <xref:System.Windows.Data.Binding> is processed, it does not return a value successfully because it is sleeping for 5 seconds, so the next <xref:System.Windows.Data.Binding> element is processed.</span></span> <span data-ttu-id="5759f-118">La siguiente <xref:System.Windows.Data.Binding> no devuelve un valor correctamente porque está inactivo durante 3 segundos.</span><span class="sxs-lookup"><span data-stu-id="5759f-118">The next <xref:System.Windows.Data.Binding> does not return a value successfully because it is sleeping for 3 seconds.</span></span> <span data-ttu-id="5759f-119">El motor de enlace, a continuación, se desplaza al siguiente <xref:System.Windows.Data.Binding> elemento, que está enlazado a la `FastDP` propiedad.</span><span class="sxs-lookup"><span data-stu-id="5759f-119">The binding engine then moves onto the next <xref:System.Windows.Data.Binding> element, which is bound to the `FastDP` property.</span></span> <span data-ttu-id="5759f-120">Esto <xref:System.Windows.Data.Binding> devuelve el valor "Fast Value".</span><span class="sxs-lookup"><span data-stu-id="5759f-120">This <xref:System.Windows.Data.Binding> returns the value "Fast Value".</span></span> <span data-ttu-id="5759f-121">El <xref:System.Windows.Controls.TextBlock> ahora muestra el valor "Fast Value".</span><span class="sxs-lookup"><span data-stu-id="5759f-121">The <xref:System.Windows.Controls.TextBlock> now displays the value "Fast Value".</span></span>  
  
 <span data-ttu-id="5759f-122">Transcurrido 3 segundos, el `SlowerDP` propiedad devuelve el valor "Slower Value".</span><span class="sxs-lookup"><span data-stu-id="5759f-122">After 3 seconds elapses, the `SlowerDP` property returns the value "Slower Value".</span></span> <span data-ttu-id="5759f-123">El <xref:System.Windows.Controls.TextBlock> , a continuación, muestra el valor "Slower Value".</span><span class="sxs-lookup"><span data-stu-id="5759f-123">The <xref:System.Windows.Controls.TextBlock> then displays the value "Slower Value".</span></span>  
  
 <span data-ttu-id="5759f-124">Transcurrido de 5 segundos, la `SlowestDP` propiedad devuelve el valor "más lento".</span><span class="sxs-lookup"><span data-stu-id="5759f-124">After 5 seconds elapses, the `SlowestDP` property returns the value "Slowest Value".</span></span> <span data-ttu-id="5759f-125">Ese enlace tiene la prioridad más alta, ya que aparece en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="5759f-125">That binding has the highest priority because it is listed first.</span></span> <span data-ttu-id="5759f-126">El <xref:System.Windows.Controls.TextBlock> ahora muestra el valor "más lento".</span><span class="sxs-lookup"><span data-stu-id="5759f-126">The <xref:System.Windows.Controls.TextBlock> now displays the value "Slowest Value".</span></span>  
  
 <span data-ttu-id="5759f-127">Consulte <xref:System.Windows.Data.PriorityBinding> para obtener información sobre lo que se considera un valor devuelto correctamente de un enlace.</span><span class="sxs-lookup"><span data-stu-id="5759f-127">See <xref:System.Windows.Data.PriorityBinding> for information about what is considered a successful return value from a binding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5759f-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="5759f-128">See Also</span></span>  
 <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="5759f-129">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="5759f-129">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="5759f-130">Temas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="5759f-130">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
