---
title: 'Implementación de interfaz explícita: Guía de programación de C#'
ms.date: 01/24/2020
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: ea32a279b7c464174a7fada5ef93ccf62ef39884
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167678"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a><span data-ttu-id="b480f-102">Implementación de interfaz explícita (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="b480f-102">Explicit Interface Implementation (C# Programming Guide)</span></span>

<span data-ttu-id="b480f-103">Si una [clase](../../language-reference/keywords/class.md) implementa dos interfaces que contienen un miembro con la misma firma, entonces al implementar ese miembro en la clase ambas interfaces usarán ese miembro como su implementación.</span><span class="sxs-lookup"><span data-stu-id="b480f-103">If a [class](../../language-reference/keywords/class.md) implements two interfaces that contain a member with the same signature, then implementing that member on the class will cause both interfaces to use that member as their implementation.</span></span> <span data-ttu-id="b480f-104">En el ejemplo siguiente, todas las llamadas a `Paint` invocan el mismo método.</span><span class="sxs-lookup"><span data-stu-id="b480f-104">In the following example, all the calls to `Paint` invoke the same method.</span></span> <span data-ttu-id="b480f-105">En este primer ejemplo se definen los tipos:</span><span class="sxs-lookup"><span data-stu-id="b480f-105">This first sample defines the types:</span></span>

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefineTypes)]

<span data-ttu-id="b480f-106">En el ejemplo siguiente se llama a los métodos:</span><span class="sxs-lookup"><span data-stu-id="b480f-106">The following sample calls the methods:</span></span>

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallMethods)]

<span data-ttu-id="b480f-107">Cuando dos miembros de interfaz no realizan la misma función, puede provocar una implementación incorrecta de una o ambas interfaces.</span><span class="sxs-lookup"><span data-stu-id="b480f-107">When two interface members don't perform the same function, it leads to an incorrect implementation of one or both of the interfaces.</span></span> <span data-ttu-id="b480f-108">Es posible implementar un miembro de interfaz de manera explícita: mediante la creación de un miembro de clase que solo se llama a través de la interfaz, y es específico de esa interfaz.</span><span class="sxs-lookup"><span data-stu-id="b480f-108">It's possible to implement an interface member explicitly—creating a class member that is only called through the interface, and is specific to that interface.</span></span> <span data-ttu-id="b480f-109">Asigne al miembro de clase el nombre de la interfaz y un punto.</span><span class="sxs-lookup"><span data-stu-id="b480f-109">Name the class member with the name of the interface and a period.</span></span> <span data-ttu-id="b480f-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b480f-110">For example:</span></span>

[!code-csharp[DefineExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#ExplicitImplementation)]

<span data-ttu-id="b480f-111">El miembro de clase `IControl.Paint` solo está disponible a través de la interfaz `IControl`, y `ISurface.Paint` solo está disponible mediante `ISurface`.</span><span class="sxs-lookup"><span data-stu-id="b480f-111">The class member `IControl.Paint` is only available through the `IControl` interface, and `ISurface.Paint` is only available through `ISurface`.</span></span> <span data-ttu-id="b480f-112">Las dos implementaciones de método son independientes, y ninguna está disponible directamente en la clase.</span><span class="sxs-lookup"><span data-stu-id="b480f-112">Both method implementations are separate, and neither are available directly on the class.</span></span> <span data-ttu-id="b480f-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b480f-113">For example:</span></span>

[!code-csharp[CallExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallExplicitImplementation)]

<span data-ttu-id="b480f-114">La implementación explícita también se usa para resolver casos donde dos interfaces declaran miembros diferentes del mismo nombre como una propiedad y un método.</span><span class="sxs-lookup"><span data-stu-id="b480f-114">Explicit implementation is also used to resolve cases where two interfaces each declare different members of the same name such as a property and a method.</span></span> <span data-ttu-id="b480f-115">Para implementar ambas interfaces, una clase tiene que usar la implementación explícita para la propiedad `P` o el método `P`, o ambos, para evitar un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="b480f-115">To implement both interfaces, a class has to use explicit implementation either for the property `P`, or the method `P`, or both, to avoid a compiler error.</span></span> <span data-ttu-id="b480f-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b480f-116">For example:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#NameCollision)]

<span data-ttu-id="b480f-117">A partir de [C# 8.0](../../whats-new/csharp-8.md#default-interface-methods), se puede definir una implementación para los miembros declarados en una interfaz.</span><span class="sxs-lookup"><span data-stu-id="b480f-117">Beginning with [C# 8.0](../../whats-new/csharp-8.md#default-interface-methods), you can define an implementation for members declared in an interface.</span></span> <span data-ttu-id="b480f-118">Si una clase hereda una implementación de método de una interfaz, ese método solo es accesible a través de una referencia del tipo de interfaz.</span><span class="sxs-lookup"><span data-stu-id="b480f-118">If a class inherits a method implementation from an interface, that method is only accessible through a reference of the interface type.</span></span> <span data-ttu-id="b480f-119">El miembro heredado no aparece como parte de la interfaz pública.</span><span class="sxs-lookup"><span data-stu-id="b480f-119">The inherited member doesn't appear as part of the public interface.</span></span> <span data-ttu-id="b480f-120">En el ejemplo siguiente se define una implementación predeterminada para un método de interfaz:</span><span class="sxs-lookup"><span data-stu-id="b480f-120">The following sample defines a default implementation for an interface method:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefaultImplementation)]

<span data-ttu-id="b480f-121">En el ejemplo siguiente se invoca la implementación predeterminada:</span><span class="sxs-lookup"><span data-stu-id="b480f-121">The following sample invokes the default implementation:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallDefaultImplementation)]

<span data-ttu-id="b480f-122">Cualquier clase que implemente la interfaz `IControl` puede invalidar el método `Paint` predeterminado, ya sea como un método público, o bien como una implementación de interfaz explícita.</span><span class="sxs-lookup"><span data-stu-id="b480f-122">Any class that implements the `IControl` interface can override the default `Paint` method, either as a public method, or as an explicit interface implementation.</span></span>

## <a name="see-also"></a><span data-ttu-id="b480f-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="b480f-123">See also</span></span>

- [<span data-ttu-id="b480f-124">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="b480f-124">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b480f-125">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="b480f-125">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="b480f-126">Interfaces</span><span class="sxs-lookup"><span data-stu-id="b480f-126">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="b480f-127">Herencia</span><span class="sxs-lookup"><span data-stu-id="b480f-127">Inheritance</span></span>](../classes-and-structs/inheritance.md)
