---
title: 'Implementación de interfaz explícita: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: ac90726fd50f104d1b9251d4f9b097b721ea5e7d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75701763"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a><span data-ttu-id="cd692-102">Implementación de interfaz explícita (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="cd692-102">Explicit Interface Implementation (C# Programming Guide)</span></span>
<span data-ttu-id="cd692-103">Si una [clase](../../language-reference/keywords/class.md) implementa dos interfaces que contienen un miembro con la misma firma, entonces al implementar ese miembro en la clase ambas interfaces usarán ese miembro como su implementación.</span><span class="sxs-lookup"><span data-stu-id="cd692-103">If a [class](../../language-reference/keywords/class.md) implements two interfaces that contain a member with the same signature, then implementing that member on the class will cause both interfaces to use that member as their implementation.</span></span> <span data-ttu-id="cd692-104">En el ejemplo siguiente, todas las llamadas a `Paint` invocan el mismo método.</span><span class="sxs-lookup"><span data-stu-id="cd692-104">In the following example, all the calls to `Paint` invoke the same method.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#39)]  
  
 <span data-ttu-id="cd692-105">En cambio, si los dos miembros de [interfaz](../../language-reference/keywords/interface.md) no realizan la misma función, esto puede provocar una implementación incorrecta de una o ambas interfaces.</span><span class="sxs-lookup"><span data-stu-id="cd692-105">If the two [interface](../../language-reference/keywords/interface.md) members do not perform the same function, however, this can lead to an incorrect implementation of one or both of the interfaces.</span></span> <span data-ttu-id="cd692-106">Es posible implementar un miembro de interfaz explícitamente, mediante la creación de un miembro de clase que solo se llama a través de la interfaz, y es específico de esa interfaz.</span><span class="sxs-lookup"><span data-stu-id="cd692-106">It is possible to implement an interface member explicitly—creating a class member that is only called through the interface, and is specific to that interface.</span></span> <span data-ttu-id="cd692-107">Esto se consigue asignando un nombre al miembro de clase con el nombre de la interfaz y un período.</span><span class="sxs-lookup"><span data-stu-id="cd692-107">This is accomplished by naming the class member with the name of the interface and a period.</span></span> <span data-ttu-id="cd692-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cd692-108">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#40)]  
  
 <span data-ttu-id="cd692-109">El miembro de clase `IControl.Paint` solo está disponible a través de la interfaz `IControl`, y `ISurface.Paint` solo está disponible mediante `ISurface`.</span><span class="sxs-lookup"><span data-stu-id="cd692-109">The class member `IControl.Paint` is only available through the `IControl` interface, and `ISurface.Paint` is only available through `ISurface`.</span></span> <span data-ttu-id="cd692-110">Ambas implementaciones de método son independientes, y ninguna está disponible directamente en la clase.</span><span class="sxs-lookup"><span data-stu-id="cd692-110">Both method implementations are separate, and neither is available directly on the class.</span></span> <span data-ttu-id="cd692-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cd692-111">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#41)]  
  
 <span data-ttu-id="cd692-112">La implementación explícita también se usa para resolver casos donde dos interfaces declaran miembros diferentes del mismo nombre como una propiedad y un método:</span><span class="sxs-lookup"><span data-stu-id="cd692-112">Explicit implementation is also used to resolve cases where two interfaces each declare different members of the same name such as a property and a method:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#42](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#42)]  
  
 <span data-ttu-id="cd692-113">Para implementar ambas interfaces, una clase tiene que usar la implementación explícita para la propiedad P, o el método P o ambos, para evitar un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="cd692-113">To implement both interfaces, a class has to use explicit implementation either for the property P, or the method P, or both, to avoid a compiler error.</span></span> <span data-ttu-id="cd692-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cd692-114">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#43](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#43)]  
  
## <a name="see-also"></a><span data-ttu-id="cd692-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd692-115">See also</span></span>

- [<span data-ttu-id="cd692-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="cd692-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="cd692-117">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="cd692-117">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="cd692-118">Interfaces</span><span class="sxs-lookup"><span data-stu-id="cd692-118">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="cd692-119">Herencia</span><span class="sxs-lookup"><span data-stu-id="cd692-119">Inheritance</span></span>](../classes-and-structs/inheritance.md)
