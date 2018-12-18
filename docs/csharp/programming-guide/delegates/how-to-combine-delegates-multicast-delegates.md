---
title: 'Procedimiento Combinar delegados (delegados de multidifusión): Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: d835f9b22fef550d6e73cbd620a283bd71e393ec
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237797"
---
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a><span data-ttu-id="ddccd-102">Procedimiento Combinar delegados (delegados de multidifusión) (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="ddccd-102">How to: Combine Delegates (Multicast Delegates)(C# Programming Guide)</span></span>
<span data-ttu-id="ddccd-103">En este ejemplo se muestra cómo crear delegados de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="ddccd-103">This example demonstrates how to create multicast delegates.</span></span> <span data-ttu-id="ddccd-104">Una propiedad útil de los objetos [delegados](../../../csharp/language-reference/keywords/delegate.md) es que puedan asignarse objetos múltiples a una instancia de delegado con el operador `+`.</span><span class="sxs-lookup"><span data-stu-id="ddccd-104">A useful property of [delegate](../../../csharp/language-reference/keywords/delegate.md) objects is that multiple objects can be assigned to one delegate instance by using the `+` operator.</span></span> <span data-ttu-id="ddccd-105">El delegado de multidifusión contiene una lista de los delegados asignados.</span><span class="sxs-lookup"><span data-stu-id="ddccd-105">The multicast delegate contains a list of the assigned delegates.</span></span> <span data-ttu-id="ddccd-106">Cuando se llama al delegado de multidifusión, invoca a los delegados de la lista, en orden.</span><span class="sxs-lookup"><span data-stu-id="ddccd-106">When the multicast delegate is called, it invokes the delegates in the list, in order.</span></span> <span data-ttu-id="ddccd-107">Solo los delegados del mismo tipo pueden combinarse.</span><span class="sxs-lookup"><span data-stu-id="ddccd-107">Only delegates of the same type can be combined.</span></span>  
  
 <span data-ttu-id="ddccd-108">El operador `-` puede usarse para quitar un delegado de componente de un delegado de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="ddccd-108">The `-` operator can be used to remove a component delegate from a multicast delegate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddccd-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ddccd-109">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-combine-delegates-multicast-delegates_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="ddccd-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="ddccd-110">See Also</span></span>

- <xref:System.MulticastDelegate>  
- [<span data-ttu-id="ddccd-111">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ddccd-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="ddccd-112">Eventos</span><span class="sxs-lookup"><span data-stu-id="ddccd-112">Events</span></span>](../../../csharp/programming-guide/events/index.md)
