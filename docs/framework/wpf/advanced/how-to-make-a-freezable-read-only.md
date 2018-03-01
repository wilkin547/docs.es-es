---
title: "Cómo: Hacer que un elemento Freezable sea de sólo lectura"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aa6d3f7109e8258dff0a07556bc8572f6071c961
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-a-freezable-read-only"></a><span data-ttu-id="4200d-102">Cómo: Hacer que un elemento Freezable sea de sólo lectura</span><span class="sxs-lookup"><span data-stu-id="4200d-102">How to: Make a Freezable Read-Only</span></span>
<span data-ttu-id="4200d-103">Este ejemplo muestra cómo realizar una <xref:System.Windows.Freezable> -solo lectura mediante una llamada a su <xref:System.Windows.Freezable.Freeze%2A> método.</span><span class="sxs-lookup"><span data-stu-id="4200d-103">This example shows how to make a <xref:System.Windows.Freezable> read-only by calling its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span>  
  
 <span data-ttu-id="4200d-104">No se pueden inmovilizar un <xref:System.Windows.Freezable> objeto si alguna de las condiciones siguientes es `true` sobre el objeto:</span><span class="sxs-lookup"><span data-stu-id="4200d-104">You cannot freeze a <xref:System.Windows.Freezable> object if any one of the following conditions is `true` about the object:</span></span>  
  
-   <span data-ttu-id="4200d-105">Ha animado o propiedades enlazado a datos.</span><span class="sxs-lookup"><span data-stu-id="4200d-105">It has animated or data bound properties.</span></span>  
  
-   <span data-ttu-id="4200d-106">Dicha clase tiene propiedades establecidas por un recurso dinámico.</span><span class="sxs-lookup"><span data-stu-id="4200d-106">It has properties that are set by a dynamic resource.</span></span> <span data-ttu-id="4200d-107">Para obtener más información acerca de recursos dinámicos, consulte el [recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="4200d-107">For more information about dynamic resources, see the [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
-   <span data-ttu-id="4200d-108">Contiene <xref:System.Windows.Freezable> objetos secundarios que no se pueden inmovilizar.</span><span class="sxs-lookup"><span data-stu-id="4200d-108">It contains <xref:System.Windows.Freezable> sub-objects that cannot be frozen.</span></span>  
  
 <span data-ttu-id="4200d-109">Si estas condiciones no son `false` para su <xref:System.Windows.Freezable> objeto y no tiene intención de modificarlo, considere la posibilidad de inmovilización para obtener mejoras de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="4200d-109">If these conditions are `false` for your <xref:System.Windows.Freezable> object and you do not intend to modify it, consider freezing it to gain performance benefits.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4200d-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4200d-110">Example</span></span>  
 <span data-ttu-id="4200d-111">En el ejemplo siguiente se inmoviliza un <xref:System.Windows.Media.SolidColorBrush>, que es un tipo de <xref:System.Windows.Freezable> objeto.</span><span class="sxs-lookup"><span data-stu-id="4200d-111">The following example freezes a <xref:System.Windows.Media.SolidColorBrush>, which is a type of <xref:System.Windows.Freezable> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 <span data-ttu-id="4200d-112">Para obtener más información acerca de <xref:System.Windows.Freezable> los objetos, vea la [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4200d-112">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4200d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="4200d-113">See Also</span></span>  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.CanFreeze%2A>  
 <xref:System.Windows.Freezable.Freeze%2A>  
 [<span data-ttu-id="4200d-114">Información general sobre objetos Freezable</span><span class="sxs-lookup"><span data-stu-id="4200d-114">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="4200d-115">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="4200d-115">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
