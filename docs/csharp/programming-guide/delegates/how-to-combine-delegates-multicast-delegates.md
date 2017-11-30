---
title: "Cómo: Combinar delegados (delegados de multidifusión) (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ddb4ecbbf456179e91aa0003c2dc5653f153411f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a><span data-ttu-id="9b1a6-102">Cómo: Combinar delegados (delegados de multidifusión) (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="9b1a6-102">How to: Combine Delegates (Multicast Delegates)(C# Programming Guide)</span></span>
<span data-ttu-id="9b1a6-103">En este ejemplo se muestra cómo crear delegados de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="9b1a6-103">This example demonstrates how to create multicast delegates.</span></span> <span data-ttu-id="9b1a6-104">Una propiedad útil de los objetos [delegados](../../../csharp/language-reference/keywords/delegate.md) es que puedan asignarse objetos múltiples a una instancia de delegado con el operador `+`.</span><span class="sxs-lookup"><span data-stu-id="9b1a6-104">A useful property of [delegate](../../../csharp/language-reference/keywords/delegate.md) objects is that multiple objects can be assigned to one delegate instance by using the `+` operator.</span></span> <span data-ttu-id="9b1a6-105">El delegado de multidifusión contiene una lista de los delegados asignados.</span><span class="sxs-lookup"><span data-stu-id="9b1a6-105">The multicast delegate contains a list of the assigned delegates.</span></span> <span data-ttu-id="9b1a6-106">Cuando se llama al delegado de multidifusión, invoca a los delegados de la lista, en orden.</span><span class="sxs-lookup"><span data-stu-id="9b1a6-106">When the multicast delegate is called, it invokes the delegates in the list, in order.</span></span> <span data-ttu-id="9b1a6-107">Solo los delegados del mismo tipo pueden combinarse.</span><span class="sxs-lookup"><span data-stu-id="9b1a6-107">Only delegates of the same type can be combined.</span></span>  
  
 <span data-ttu-id="9b1a6-108">El operador `-` puede usarse para quitar un delegado de componente de un delegado de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="9b1a6-108">The `-` operator can be used to remove a component delegate from a multicast delegate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b1a6-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9b1a6-109">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-combine-delegates-multicast-delegates_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="9b1a6-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b1a6-110">See Also</span></span>  
 <xref:System.MulticastDelegate>  
 [<span data-ttu-id="9b1a6-111">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9b1a6-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9b1a6-112">Eventos</span><span class="sxs-lookup"><span data-stu-id="9b1a6-112">Events</span></span>](../../../csharp/programming-guide/events/index.md)
