---
title: 'Procedimiento para combinar delegados (delegados de multidifusión): Guía de programación de C#'
description: Aprenda a combinar delegados para crear delegados de multidifusión. Vea un ejemplo de código y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: 3e86c8ed4b7b091ee8c75930d427c22aa5bc0c52
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185956"
---
# <a name="how-to-combine-delegates-multicast-delegates-c-programming-guide"></a><span data-ttu-id="27c95-104">Procedimiento para combinar delegados (delegados de multidifusión) (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="27c95-104">How to combine delegates (Multicast Delegates) (C# Programming Guide)</span></span>

<span data-ttu-id="27c95-105">En este ejemplo se muestra cómo crear delegados de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="27c95-105">This example demonstrates how to create multicast delegates.</span></span> <span data-ttu-id="27c95-106">Una propiedad útil de los objetos [delegados](../../language-reference/builtin-types/reference-types.md) es que puedan asignarse objetos múltiples a una instancia de delegado con el operador `+`.</span><span class="sxs-lookup"><span data-stu-id="27c95-106">A useful property of [delegate](../../language-reference/builtin-types/reference-types.md) objects is that multiple objects can be assigned to one delegate instance by using the `+` operator.</span></span> <span data-ttu-id="27c95-107">El delegado de multidifusión contiene una lista de los delegados asignados.</span><span class="sxs-lookup"><span data-stu-id="27c95-107">The multicast delegate contains a list of the assigned delegates.</span></span> <span data-ttu-id="27c95-108">Cuando se llama al delegado de multidifusión, invoca a los delegados de la lista, en orden.</span><span class="sxs-lookup"><span data-stu-id="27c95-108">When the multicast delegate is called, it invokes the delegates in the list, in order.</span></span> <span data-ttu-id="27c95-109">Solo los delegados del mismo tipo pueden combinarse.</span><span class="sxs-lookup"><span data-stu-id="27c95-109">Only delegates of the same type can be combined.</span></span>  
  
 <span data-ttu-id="27c95-110">El operador `-` puede usarse para quitar un delegado de componente de un delegado de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="27c95-110">The `-` operator can be used to remove a component delegate from a multicast delegate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27c95-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="27c95-111">Example</span></span>  

 [!code-csharp[csProgGuideDelegates#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="27c95-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="27c95-112">See also</span></span>

- <xref:System.MulticastDelegate>
- [<span data-ttu-id="27c95-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="27c95-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="27c95-114">Eventos</span><span class="sxs-lookup"><span data-stu-id="27c95-114">Events</span></span>](../events/index.md)
