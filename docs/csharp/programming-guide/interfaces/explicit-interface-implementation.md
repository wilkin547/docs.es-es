---
title: "Implementación de interfaz explícita (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6baf985e8031e1e859d20570168222ca8f368eff
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="explicit-interface-implementation-c-programming-guide"></a><span data-ttu-id="749f9-102">Implementación de interfaz explícita (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="749f9-102">Explicit Interface Implementation (C# Programming Guide)</span></span>
<span data-ttu-id="749f9-103">Si una [clase](../../../csharp/language-reference/keywords/class.md) implementa dos interfaces que contienen un miembro con la misma firma, entonces al implementar ese miembro en la clase ambas interfaces usarán ese miembro como su implementación.</span><span class="sxs-lookup"><span data-stu-id="749f9-103">If a [class](../../../csharp/language-reference/keywords/class.md) implements two interfaces that contain a member with the same signature, then implementing that member on the class will cause both interfaces to use that member as their implementation.</span></span> <span data-ttu-id="749f9-104">En el ejemplo siguiente, todas las llamadas a `Paint` invocan el mismo método.</span><span class="sxs-lookup"><span data-stu-id="749f9-104">In the following example, all the calls to `Paint` invoke the same method.</span></span>  
  
 <span data-ttu-id="749f9-105">[!code-cs[csProgGuideInheritance#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="749f9-105">[!code-cs[csProgGuideInheritance#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_1.cs)]</span></span>  
  
 <span data-ttu-id="749f9-106">En cambio, si los dos miembros de [interfaz](../../../csharp/language-reference/keywords/interface.md) no realizan la misma función, esto puede provocar una implementación incorrecta de una o ambas interfaces.</span><span class="sxs-lookup"><span data-stu-id="749f9-106">If the two [interface](../../../csharp/language-reference/keywords/interface.md) members do not perform the same function, however, this can lead to an incorrect implementation of one or both of the interfaces.</span></span> <span data-ttu-id="749f9-107">Es posible implementar un miembro de interfaz explícitamente, mediante la creación de un miembro de clase que solo se llama a través de la interfaz, y es específico de esa interfaz.</span><span class="sxs-lookup"><span data-stu-id="749f9-107">It is possible to implement an interface member explicitly—creating a class member that is only called through the interface, and is specific to that interface.</span></span> <span data-ttu-id="749f9-108">Esto se consigue asignando un nombre al miembro de clase con el nombre de la interfaz y un período.</span><span class="sxs-lookup"><span data-stu-id="749f9-108">This is accomplished by naming the class member with the name of the interface and a period.</span></span> <span data-ttu-id="749f9-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="749f9-109">For example:</span></span>  
  
 <span data-ttu-id="749f9-110">[!code-cs[csProgGuideInheritance#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="749f9-110">[!code-cs[csProgGuideInheritance#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_2.cs)]</span></span>  
  
 <span data-ttu-id="749f9-111">El miembro de clase `IControl.Paint` solo está disponible a través de la interfaz `IControl`, y `ISurface.Paint` solo está disponible mediante `ISurface`.</span><span class="sxs-lookup"><span data-stu-id="749f9-111">The class member `IControl.Paint` is only available through the `IControl` interface, and `ISurface.Paint` is only available through `ISurface`.</span></span> <span data-ttu-id="749f9-112">Ambas implementaciones de método son independientes, y ninguna está disponible directamente en la clase.</span><span class="sxs-lookup"><span data-stu-id="749f9-112">Both method implementations are separate, and neither is available directly on the class.</span></span> <span data-ttu-id="749f9-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="749f9-113">For example:</span></span>  
  
 <span data-ttu-id="749f9-114">[!code-cs[csProgGuideInheritance#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="749f9-114">[!code-cs[csProgGuideInheritance#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_3.cs)]</span></span>  
  
 <span data-ttu-id="749f9-115">La implementación explícita también se usa para resolver casos donde dos interfaces declaran miembros diferentes del mismo nombre como una propiedad y un método:</span><span class="sxs-lookup"><span data-stu-id="749f9-115">Explicit implementation is also used to resolve cases where two interfaces each declare different members of the same name such as a property and a method:</span></span>  
  
 <span data-ttu-id="749f9-116">[!code-cs[csProgGuideInheritance#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="749f9-116">[!code-cs[csProgGuideInheritance#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_4.cs)]</span></span>  
  
 <span data-ttu-id="749f9-117">Para implementar ambas interfaces, una clase tiene que usar la implementación explícita para la propiedad P, o el método P o ambos, para evitar un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="749f9-117">To implement both interfaces, a class has to use explicit implementation either for the property P, or the method P, or both, to avoid a compiler error.</span></span> <span data-ttu-id="749f9-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="749f9-118">For example:</span></span>  
  
 <span data-ttu-id="749f9-119">[!code-cs[csProgGuideInheritance#43](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="749f9-119">[!code-cs[csProgGuideInheritance#43](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_5.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="749f9-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="749f9-120">See Also</span></span>  
 <span data-ttu-id="749f9-121">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="749f9-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="749f9-122">[Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="749f9-122">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="749f9-123">[Interfaces](../../../csharp/programming-guide/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="749f9-123">[Interfaces](../../../csharp/programming-guide/interfaces/index.md) </span></span>  
 [<span data-ttu-id="749f9-124">Herencia</span><span class="sxs-lookup"><span data-stu-id="749f9-124">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)

