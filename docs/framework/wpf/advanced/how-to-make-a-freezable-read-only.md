---
title: 'Cómo: Hacer que un elemento Freezable sea de sólo lectura'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: 4185966d864be425bc631953461f6f27ab983bee
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460072"
---
# <a name="how-to-make-a-freezable-read-only"></a><span data-ttu-id="9fffa-102">Cómo: Hacer que un elemento Freezable sea de sólo lectura</span><span class="sxs-lookup"><span data-stu-id="9fffa-102">How to: Make a Freezable Read-Only</span></span>
<span data-ttu-id="9fffa-103">En este ejemplo se muestra cómo crear un <xref:System.Windows.Freezable> de solo lectura llamando a su método <xref:System.Windows.Freezable.Freeze%2A>.</span><span class="sxs-lookup"><span data-stu-id="9fffa-103">This example shows how to make a <xref:System.Windows.Freezable> read-only by calling its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span>  
  
 <span data-ttu-id="9fffa-104">No se puede inmovilizar un objeto <xref:System.Windows.Freezable> si alguna de las condiciones siguientes se `true` sobre el objeto:</span><span class="sxs-lookup"><span data-stu-id="9fffa-104">You cannot freeze a <xref:System.Windows.Freezable> object if any one of the following conditions is `true` about the object:</span></span>  
  
- <span data-ttu-id="9fffa-105">Tiene propiedades animadas o enlazadas a datos.</span><span class="sxs-lookup"><span data-stu-id="9fffa-105">It has animated or data bound properties.</span></span>  
  
- <span data-ttu-id="9fffa-106">Tiene propiedades establecidas por un recurso dinámico.</span><span class="sxs-lookup"><span data-stu-id="9fffa-106">It has properties that are set by a dynamic resource.</span></span> <span data-ttu-id="9fffa-107">Para obtener más información sobre los recursos dinámicos, vea los [recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span><span class="sxs-lookup"><span data-stu-id="9fffa-107">For more information about dynamic resources, see the [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>  
  
- <span data-ttu-id="9fffa-108">Contiene <xref:System.Windows.Freezable> subobjetos que no se pueden inmovilizar.</span><span class="sxs-lookup"><span data-stu-id="9fffa-108">It contains <xref:System.Windows.Freezable> sub-objects that cannot be frozen.</span></span>  
  
 <span data-ttu-id="9fffa-109">Si estas condiciones se `false` para el objeto <xref:System.Windows.Freezable> y no pretende modificarla, considere la posibilidad de inmovilizarla para obtener ventajas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="9fffa-109">If these conditions are `false` for your <xref:System.Windows.Freezable> object and you do not intend to modify it, consider freezing it to gain performance benefits.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fffa-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9fffa-110">Example</span></span>  
 <span data-ttu-id="9fffa-111">En el ejemplo siguiente se inmoviliza un <xref:System.Windows.Media.SolidColorBrush>, que es un tipo de <xref:System.Windows.Freezable> objeto.</span><span class="sxs-lookup"><span data-stu-id="9fffa-111">The following example freezes a <xref:System.Windows.Media.SolidColorBrush>, which is a type of <xref:System.Windows.Freezable> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 <span data-ttu-id="9fffa-112">Para obtener más información acerca de los objetos de <xref:System.Windows.Freezable>, consulte la [información general sobre objetos Freezable](freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9fffa-112">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fffa-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fffa-113">See also</span></span>

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [<span data-ttu-id="9fffa-114">Información general sobre objetos Freezable</span><span class="sxs-lookup"><span data-stu-id="9fffa-114">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="9fffa-115">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="9fffa-115">How-to Topics</span></span>](base-elements-how-to-topics.md)
