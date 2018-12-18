---
title: 'Implementación de interfaz explícita: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: e985da878ca4160938f29911d4313ee6cd731aeb
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244835"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a><span data-ttu-id="7611c-102">Implementación de interfaz explícita (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="7611c-102">Explicit Interface Implementation (C# Programming Guide)</span></span>
<span data-ttu-id="7611c-103">Si una [clase](../../../csharp/language-reference/keywords/class.md) implementa dos interfaces que contienen un miembro con la misma firma, entonces al implementar ese miembro en la clase ambas interfaces usarán ese miembro como su implementación.</span><span class="sxs-lookup"><span data-stu-id="7611c-103">If a [class](../../../csharp/language-reference/keywords/class.md) implements two interfaces that contain a member with the same signature, then implementing that member on the class will cause both interfaces to use that member as their implementation.</span></span> <span data-ttu-id="7611c-104">En el ejemplo siguiente, todas las llamadas a `Paint` invocan el mismo método.</span><span class="sxs-lookup"><span data-stu-id="7611c-104">In the following example, all the calls to `Paint` invoke the same method.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_1.cs)]  
  
 <span data-ttu-id="7611c-105">En cambio, si los dos miembros de [interfaz](../../../csharp/language-reference/keywords/interface.md) no realizan la misma función, esto puede provocar una implementación incorrecta de una o ambas interfaces.</span><span class="sxs-lookup"><span data-stu-id="7611c-105">If the two [interface](../../../csharp/language-reference/keywords/interface.md) members do not perform the same function, however, this can lead to an incorrect implementation of one or both of the interfaces.</span></span> <span data-ttu-id="7611c-106">Es posible implementar un miembro de interfaz explícitamente, mediante la creación de un miembro de clase que solo se llama a través de la interfaz, y es específico de esa interfaz.</span><span class="sxs-lookup"><span data-stu-id="7611c-106">It is possible to implement an interface member explicitly—creating a class member that is only called through the interface, and is specific to that interface.</span></span> <span data-ttu-id="7611c-107">Esto se consigue asignando un nombre al miembro de clase con el nombre de la interfaz y un período.</span><span class="sxs-lookup"><span data-stu-id="7611c-107">This is accomplished by naming the class member with the name of the interface and a period.</span></span> <span data-ttu-id="7611c-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7611c-108">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_2.cs)]  
  
 <span data-ttu-id="7611c-109">El miembro de clase `IControl.Paint` solo está disponible a través de la interfaz `IControl`, y `ISurface.Paint` solo está disponible mediante `ISurface`.</span><span class="sxs-lookup"><span data-stu-id="7611c-109">The class member `IControl.Paint` is only available through the `IControl` interface, and `ISurface.Paint` is only available through `ISurface`.</span></span> <span data-ttu-id="7611c-110">Ambas implementaciones de método son independientes, y ninguna está disponible directamente en la clase.</span><span class="sxs-lookup"><span data-stu-id="7611c-110">Both method implementations are separate, and neither is available directly on the class.</span></span> <span data-ttu-id="7611c-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7611c-111">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_3.cs)]  
  
 <span data-ttu-id="7611c-112">La implementación explícita también se usa para resolver casos donde dos interfaces declaran miembros diferentes del mismo nombre como una propiedad y un método:</span><span class="sxs-lookup"><span data-stu-id="7611c-112">Explicit implementation is also used to resolve cases where two interfaces each declare different members of the same name such as a property and a method:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_4.cs)]  
  
 <span data-ttu-id="7611c-113">Para implementar ambas interfaces, una clase tiene que usar la implementación explícita para la propiedad P, o el método P o ambos, para evitar un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="7611c-113">To implement both interfaces, a class has to use explicit implementation either for the property P, or the method P, or both, to avoid a compiler error.</span></span> <span data-ttu-id="7611c-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7611c-114">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#43](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_5.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="7611c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7611c-115">See Also</span></span>

- [<span data-ttu-id="7611c-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="7611c-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="7611c-117">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="7611c-117">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [<span data-ttu-id="7611c-118">Interfaces</span><span class="sxs-lookup"><span data-stu-id="7611c-118">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
- [<span data-ttu-id="7611c-119">Herencia</span><span class="sxs-lookup"><span data-stu-id="7611c-119">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)
