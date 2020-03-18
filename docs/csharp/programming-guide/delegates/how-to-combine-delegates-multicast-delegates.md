---
title: 'Procedimiento para combinar delegados (delegados de multidifusión): Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: 7b5b9ba5c9bf70983fac9f869836b4c8c5449eca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705384"
---
# <a name="how-to-combine-delegates-multicast-delegates-c-programming-guide"></a><span data-ttu-id="38536-102">Procedimiento para combinar delegados (delegados de multidifusión) (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="38536-102">How to combine delegates (Multicast Delegates) (C# Programming Guide)</span></span>
<span data-ttu-id="38536-103">En este ejemplo se muestra cómo crear delegados de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="38536-103">This example demonstrates how to create multicast delegates.</span></span> <span data-ttu-id="38536-104">Una propiedad útil de los objetos [delegados](../../language-reference/builtin-types/reference-types.md) es que puedan asignarse objetos múltiples a una instancia de delegado con el operador `+`.</span><span class="sxs-lookup"><span data-stu-id="38536-104">A useful property of [delegate](../../language-reference/builtin-types/reference-types.md) objects is that multiple objects can be assigned to one delegate instance by using the `+` operator.</span></span> <span data-ttu-id="38536-105">El delegado de multidifusión contiene una lista de los delegados asignados.</span><span class="sxs-lookup"><span data-stu-id="38536-105">The multicast delegate contains a list of the assigned delegates.</span></span> <span data-ttu-id="38536-106">Cuando se llama al delegado de multidifusión, invoca a los delegados de la lista, en orden.</span><span class="sxs-lookup"><span data-stu-id="38536-106">When the multicast delegate is called, it invokes the delegates in the list, in order.</span></span> <span data-ttu-id="38536-107">Solo los delegados del mismo tipo pueden combinarse.</span><span class="sxs-lookup"><span data-stu-id="38536-107">Only delegates of the same type can be combined.</span></span>  
  
 <span data-ttu-id="38536-108">El operador `-` puede usarse para quitar un delegado de componente de un delegado de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="38536-108">The `-` operator can be used to remove a component delegate from a multicast delegate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38536-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="38536-109">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="38536-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="38536-110">See also</span></span>

- <xref:System.MulticastDelegate>
- [<span data-ttu-id="38536-111">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="38536-111">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="38536-112">Eventos</span><span class="sxs-lookup"><span data-stu-id="38536-112">Events</span></span>](../events/index.md)
