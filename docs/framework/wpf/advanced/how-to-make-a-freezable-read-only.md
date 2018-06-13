---
title: 'Cómo: Hacer que un elemento Freezable sea de sólo lectura'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: be3abd74a71fc711cd9f4bf6796b7d55017355ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543437"
---
# <a name="how-to-make-a-freezable-read-only"></a><span data-ttu-id="5477d-102">Cómo: Hacer que un elemento Freezable sea de sólo lectura</span><span class="sxs-lookup"><span data-stu-id="5477d-102">How to: Make a Freezable Read-Only</span></span>
<span data-ttu-id="5477d-103">Este ejemplo muestra cómo realizar una <xref:System.Windows.Freezable> -solo lectura mediante una llamada a su <xref:System.Windows.Freezable.Freeze%2A> método.</span><span class="sxs-lookup"><span data-stu-id="5477d-103">This example shows how to make a <xref:System.Windows.Freezable> read-only by calling its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span>  
  
 <span data-ttu-id="5477d-104">No se pueden inmovilizar un <xref:System.Windows.Freezable> objeto si alguna de las condiciones siguientes es `true` sobre el objeto:</span><span class="sxs-lookup"><span data-stu-id="5477d-104">You cannot freeze a <xref:System.Windows.Freezable> object if any one of the following conditions is `true` about the object:</span></span>  
  
-   <span data-ttu-id="5477d-105">Ha animado o propiedades enlazado a datos.</span><span class="sxs-lookup"><span data-stu-id="5477d-105">It has animated or data bound properties.</span></span>  
  
-   <span data-ttu-id="5477d-106">Dicha clase tiene propiedades establecidas por un recurso dinámico.</span><span class="sxs-lookup"><span data-stu-id="5477d-106">It has properties that are set by a dynamic resource.</span></span> <span data-ttu-id="5477d-107">Para obtener más información acerca de recursos dinámicos, consulte el [recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="5477d-107">For more information about dynamic resources, see the [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
-   <span data-ttu-id="5477d-108">Contiene <xref:System.Windows.Freezable> objetos secundarios que no se pueden inmovilizar.</span><span class="sxs-lookup"><span data-stu-id="5477d-108">It contains <xref:System.Windows.Freezable> sub-objects that cannot be frozen.</span></span>  
  
 <span data-ttu-id="5477d-109">Si estas condiciones no son `false` para su <xref:System.Windows.Freezable> objeto y no tiene intención de modificarlo, considere la posibilidad de inmovilización para obtener mejoras de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="5477d-109">If these conditions are `false` for your <xref:System.Windows.Freezable> object and you do not intend to modify it, consider freezing it to gain performance benefits.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5477d-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5477d-110">Example</span></span>  
 <span data-ttu-id="5477d-111">En el ejemplo siguiente se inmoviliza un <xref:System.Windows.Media.SolidColorBrush>, que es un tipo de <xref:System.Windows.Freezable> objeto.</span><span class="sxs-lookup"><span data-stu-id="5477d-111">The following example freezes a <xref:System.Windows.Media.SolidColorBrush>, which is a type of <xref:System.Windows.Freezable> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 <span data-ttu-id="5477d-112">Para obtener más información acerca de <xref:System.Windows.Freezable> los objetos, vea la [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5477d-112">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5477d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5477d-113">See Also</span></span>  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.CanFreeze%2A>  
 <xref:System.Windows.Freezable.Freeze%2A>  
 [<span data-ttu-id="5477d-114">Información general sobre objetos Freezable</span><span class="sxs-lookup"><span data-stu-id="5477d-114">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="5477d-115">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="5477d-115">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
