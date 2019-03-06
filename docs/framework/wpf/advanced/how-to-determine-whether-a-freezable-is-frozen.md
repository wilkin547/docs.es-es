---
title: Filtrar Determinar si un elemento Freezable está inmovilizado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], determining if frozen
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
ms.openlocfilehash: 005bb27803830a2e38a7b143d2c4cff669ad1da6
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362518"
---
# <a name="how-to-determine-whether-a-freezable-is-frozen"></a><span data-ttu-id="8cfc7-102">Filtrar Determinar si un elemento Freezable está inmovilizado</span><span class="sxs-lookup"><span data-stu-id="8cfc7-102">How to: Determine Whether a Freezable Is Frozen</span></span>
<span data-ttu-id="8cfc7-103">En este ejemplo se muestra cómo determinar si un <xref:System.Windows.Freezable> objeto está inmovilizado.</span><span class="sxs-lookup"><span data-stu-id="8cfc7-103">This example shows how to determine whether a <xref:System.Windows.Freezable> object is frozen.</span></span> <span data-ttu-id="8cfc7-104">Si intenta modificar inmovilizado <xref:System.Windows.Freezable> objeto, produce un <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="8cfc7-104">If you try to modify a frozen <xref:System.Windows.Freezable> object, it throws an <xref:System.InvalidOperationException>.</span></span> <span data-ttu-id="8cfc7-105">Para evitar que se produzca esta excepción, use el <xref:System.Windows.Freezable.IsFrozen%2A> propiedad de la <xref:System.Windows.Freezable> objeto para determinar si se encuentra inmovilizado.</span><span class="sxs-lookup"><span data-stu-id="8cfc7-105">To avoid throwing this exception, use the <xref:System.Windows.Freezable.IsFrozen%2A> property of the <xref:System.Windows.Freezable> object to determine whether it is frozen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8cfc7-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8cfc7-106">Example</span></span>  
 <span data-ttu-id="8cfc7-107">El ejemplo siguiente se inmoviliza un <xref:System.Windows.Media.SolidColorBrush> y, a continuación, se comprueba mediante la <xref:System.Windows.Freezable.IsFrozen%2A> propiedad para determinar si se encuentra inmovilizado.</span><span class="sxs-lookup"><span data-stu-id="8cfc7-107">The following example freezes a <xref:System.Windows.Media.SolidColorBrush> and then tests it by using the <xref:System.Windows.Freezable.IsFrozen%2A> property to determine whether it is frozen.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 <span data-ttu-id="8cfc7-108">Para obtener más información acerca de <xref:System.Windows.Freezable> objetos, vea el [Freezable Objects Overview](freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8cfc7-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cfc7-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="8cfc7-109">See also</span></span>
- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.IsFrozen%2A>
- [<span data-ttu-id="8cfc7-110">Información general sobre objetos Freezable</span><span class="sxs-lookup"><span data-stu-id="8cfc7-110">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="8cfc7-111">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="8cfc7-111">How-to Topics</span></span>](base-elements-how-to-topics.md)
