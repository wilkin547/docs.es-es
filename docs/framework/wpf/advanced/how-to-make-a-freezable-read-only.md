---
title: Procedimiento Hacer que un elemento Freezable sea de solo lectura
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: 9b7102db4de0df7183355e50e3b372eac30d81b3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771025"
---
# <a name="how-to-make-a-freezable-read-only"></a><span data-ttu-id="176c3-102">Procedimiento Hacer que un elemento Freezable sea de solo lectura</span><span class="sxs-lookup"><span data-stu-id="176c3-102">How to: Make a Freezable Read-Only</span></span>
<span data-ttu-id="176c3-103">En este ejemplo se muestra cómo realizar una <xref:System.Windows.Freezable> de solo lectura mediante una llamada a su <xref:System.Windows.Freezable.Freeze%2A> método.</span><span class="sxs-lookup"><span data-stu-id="176c3-103">This example shows how to make a <xref:System.Windows.Freezable> read-only by calling its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span>  
  
 <span data-ttu-id="176c3-104">No se puede inmovilizar un <xref:System.Windows.Freezable> objeto si alguna de las condiciones siguientes es `true` sobre el objeto:</span><span class="sxs-lookup"><span data-stu-id="176c3-104">You cannot freeze a <xref:System.Windows.Freezable> object if any one of the following conditions is `true` about the object:</span></span>  
  
- <span data-ttu-id="176c3-105">Ha animado o propiedades enlazado a datos.</span><span class="sxs-lookup"><span data-stu-id="176c3-105">It has animated or data bound properties.</span></span>  
  
- <span data-ttu-id="176c3-106">Tiene propiedades establecidas por un recurso dinámico.</span><span class="sxs-lookup"><span data-stu-id="176c3-106">It has properties that are set by a dynamic resource.</span></span> <span data-ttu-id="176c3-107">Para obtener más información acerca de los recursos dinámicos, consulte el [recursos XAML](xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="176c3-107">For more information about dynamic resources, see the [XAML Resources](xaml-resources.md).</span></span>  
  
- <span data-ttu-id="176c3-108">Contiene <xref:System.Windows.Freezable> subobjetos que no se puede inmovilizar.</span><span class="sxs-lookup"><span data-stu-id="176c3-108">It contains <xref:System.Windows.Freezable> sub-objects that cannot be frozen.</span></span>  
  
 <span data-ttu-id="176c3-109">Si estas condiciones son `false` para su <xref:System.Windows.Freezable> objeto y no va a modificar, considere la posibilidad de inmovilizarlo para obtener ventajas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="176c3-109">If these conditions are `false` for your <xref:System.Windows.Freezable> object and you do not intend to modify it, consider freezing it to gain performance benefits.</span></span>  
  
## <a name="example"></a><span data-ttu-id="176c3-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="176c3-110">Example</span></span>  
 <span data-ttu-id="176c3-111">El ejemplo siguiente se inmoviliza un <xref:System.Windows.Media.SolidColorBrush>, que es un tipo de <xref:System.Windows.Freezable> objeto.</span><span class="sxs-lookup"><span data-stu-id="176c3-111">The following example freezes a <xref:System.Windows.Media.SolidColorBrush>, which is a type of <xref:System.Windows.Freezable> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 <span data-ttu-id="176c3-112">Para obtener más información acerca de <xref:System.Windows.Freezable> objetos, vea el [Freezable Objects Overview](freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="176c3-112">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="176c3-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="176c3-113">See also</span></span>

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [<span data-ttu-id="176c3-114">Información general sobre objetos Freezable</span><span class="sxs-lookup"><span data-stu-id="176c3-114">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="176c3-115">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="176c3-115">How-to Topics</span></span>](base-elements-how-to-topics.md)
