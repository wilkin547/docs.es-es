---
title: 'Cómo: Combinar delegados (delegados de multidifusión) (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: e1214a4d281dbcb9d8186770b68510d3d9a4b15f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33327400"
---
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a><span data-ttu-id="d5551-102">Cómo: Combinar delegados (delegados de multidifusión) (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="d5551-102">How to: Combine Delegates (Multicast Delegates)(C# Programming Guide)</span></span>
<span data-ttu-id="d5551-103">En este ejemplo se muestra cómo crear delegados de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="d5551-103">This example demonstrates how to create multicast delegates.</span></span> <span data-ttu-id="d5551-104">Una propiedad útil de los objetos [delegados](../../../csharp/language-reference/keywords/delegate.md) es que puedan asignarse objetos múltiples a una instancia de delegado con el operador `+`.</span><span class="sxs-lookup"><span data-stu-id="d5551-104">A useful property of [delegate](../../../csharp/language-reference/keywords/delegate.md) objects is that multiple objects can be assigned to one delegate instance by using the `+` operator.</span></span> <span data-ttu-id="d5551-105">El delegado de multidifusión contiene una lista de los delegados asignados.</span><span class="sxs-lookup"><span data-stu-id="d5551-105">The multicast delegate contains a list of the assigned delegates.</span></span> <span data-ttu-id="d5551-106">Cuando se llama al delegado de multidifusión, invoca a los delegados de la lista, en orden.</span><span class="sxs-lookup"><span data-stu-id="d5551-106">When the multicast delegate is called, it invokes the delegates in the list, in order.</span></span> <span data-ttu-id="d5551-107">Solo los delegados del mismo tipo pueden combinarse.</span><span class="sxs-lookup"><span data-stu-id="d5551-107">Only delegates of the same type can be combined.</span></span>  
  
 <span data-ttu-id="d5551-108">El operador `-` puede usarse para quitar un delegado de componente de un delegado de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="d5551-108">The `-` operator can be used to remove a component delegate from a multicast delegate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5551-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5551-109">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-combine-delegates-multicast-delegates_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="d5551-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5551-110">See Also</span></span>  
 <xref:System.MulticastDelegate>  
 [<span data-ttu-id="d5551-111">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d5551-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d5551-112">Eventos</span><span class="sxs-lookup"><span data-stu-id="d5551-112">Events</span></span>](../../../csharp/programming-guide/events/index.md)
