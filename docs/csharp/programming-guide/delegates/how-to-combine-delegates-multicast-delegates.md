---
title: 'Procedimiento Combinar delegados (delegados de multidifusión): Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: ebfcba4d2ebebe2697aa01b7109bbf50b8f144e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631560"
---
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a><span data-ttu-id="e7b9a-102">Procedimiento Combinar delegados (delegados de multidifusión) (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="e7b9a-102">How to: Combine Delegates (Multicast Delegates)(C# Programming Guide)</span></span>
<span data-ttu-id="e7b9a-103">En este ejemplo se muestra cómo crear delegados de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="e7b9a-103">This example demonstrates how to create multicast delegates.</span></span> <span data-ttu-id="e7b9a-104">Una propiedad útil de los objetos [delegados](../../../csharp/language-reference/keywords/delegate.md) es que puedan asignarse objetos múltiples a una instancia de delegado con el operador `+`.</span><span class="sxs-lookup"><span data-stu-id="e7b9a-104">A useful property of [delegate](../../../csharp/language-reference/keywords/delegate.md) objects is that multiple objects can be assigned to one delegate instance by using the `+` operator.</span></span> <span data-ttu-id="e7b9a-105">El delegado de multidifusión contiene una lista de los delegados asignados.</span><span class="sxs-lookup"><span data-stu-id="e7b9a-105">The multicast delegate contains a list of the assigned delegates.</span></span> <span data-ttu-id="e7b9a-106">Cuando se llama al delegado de multidifusión, invoca a los delegados de la lista, en orden.</span><span class="sxs-lookup"><span data-stu-id="e7b9a-106">When the multicast delegate is called, it invokes the delegates in the list, in order.</span></span> <span data-ttu-id="e7b9a-107">Solo los delegados del mismo tipo pueden combinarse.</span><span class="sxs-lookup"><span data-stu-id="e7b9a-107">Only delegates of the same type can be combined.</span></span>  
  
 <span data-ttu-id="e7b9a-108">El operador `-` puede usarse para quitar un delegado de componente de un delegado de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="e7b9a-108">The `-` operator can be used to remove a component delegate from a multicast delegate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7b9a-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e7b9a-109">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-combine-delegates-multicast-delegates_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="e7b9a-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7b9a-110">See also</span></span>

- <xref:System.MulticastDelegate>
- [<span data-ttu-id="e7b9a-111">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="e7b9a-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="e7b9a-112">Eventos</span><span class="sxs-lookup"><span data-stu-id="e7b9a-112">Events</span></span>](../../../csharp/programming-guide/events/index.md)
