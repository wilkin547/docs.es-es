---
title: 'Implementación de interfaz explícita: Guía de programación de C#'
ms.date: 01/24/2020
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: c6f1f849e0d4e831802b4c9b8b4bc3887363a34c
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628155"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a><span data-ttu-id="b20bc-102">Implementación de interfaz explícita (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="b20bc-102">Explicit Interface Implementation (C# Programming Guide)</span></span>

<span data-ttu-id="b20bc-103">Si una [clase](../../language-reference/keywords/class.md) implementa dos interfaces que contienen un miembro con la misma firma, entonces al implementar ese miembro en la clase ambas interfaces usarán ese miembro como su implementación.</span><span class="sxs-lookup"><span data-stu-id="b20bc-103">If a [class](../../language-reference/keywords/class.md) implements two interfaces that contain a member with the same signature, then implementing that member on the class will cause both interfaces to use that member as their implementation.</span></span> <span data-ttu-id="b20bc-104">En el ejemplo siguiente, todas las llamadas a `Paint` invocan el mismo método.</span><span class="sxs-lookup"><span data-stu-id="b20bc-104">In the following example, all the calls to `Paint` invoke the same method.</span></span> <span data-ttu-id="b20bc-105">En este primer ejemplo se definen los tipos:</span><span class="sxs-lookup"><span data-stu-id="b20bc-105">This first sample defines the types:</span></span>

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefineTypes)]

<span data-ttu-id="b20bc-106">En el ejemplo siguiente se llama a los métodos:</span><span class="sxs-lookup"><span data-stu-id="b20bc-106">The following sample calls the methods:</span></span>

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallMethods)]

<span data-ttu-id="b20bc-107">Cuando dos miembros de interfaz no realizan la misma función, puede provocar una implementación incorrecta de una o ambas interfaces.</span><span class="sxs-lookup"><span data-stu-id="b20bc-107">When two interface members don't perform the same function, it leads to an incorrect implementation of one or both of the interfaces.</span></span> <span data-ttu-id="b20bc-108">Es posible implementar un miembro de interfaz de manera explícita: mediante la creación de un miembro de clase que solo se llama a través de la interfaz, y es específico de esa interfaz.</span><span class="sxs-lookup"><span data-stu-id="b20bc-108">It's possible to implement an interface member explicitly—creating a class member that is only called through the interface, and is specific to that interface.</span></span> <span data-ttu-id="b20bc-109">Asigne al miembro de clase el nombre de la interfaz y un punto.</span><span class="sxs-lookup"><span data-stu-id="b20bc-109">Name the class member with the name of the interface and a period.</span></span> <span data-ttu-id="b20bc-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b20bc-110">For example:</span></span>

[!code-csharp[DefineExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#ExplicitImplementation)]

<span data-ttu-id="b20bc-111">El miembro de clase `IControl.Paint` solo está disponible a través de la interfaz `IControl`, y `ISurface.Paint` solo está disponible mediante `ISurface`.</span><span class="sxs-lookup"><span data-stu-id="b20bc-111">The class member `IControl.Paint` is only available through the `IControl` interface, and `ISurface.Paint` is only available through `ISurface`.</span></span> <span data-ttu-id="b20bc-112">Las dos implementaciones de método son independientes, y ninguna está disponible directamente en la clase.</span><span class="sxs-lookup"><span data-stu-id="b20bc-112">Both method implementations are separate, and neither are available directly on the class.</span></span> <span data-ttu-id="b20bc-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b20bc-113">For example:</span></span>

[!code-csharp[CallExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallExplicitImplementation)]

<span data-ttu-id="b20bc-114">La implementación explícita también se usa para resolver casos donde dos interfaces declaran miembros diferentes del mismo nombre como una propiedad y un método.</span><span class="sxs-lookup"><span data-stu-id="b20bc-114">Explicit implementation is also used to resolve cases where two interfaces each declare different members of the same name such as a property and a method.</span></span> <span data-ttu-id="b20bc-115">Para implementar ambas interfaces, una clase tiene que usar la implementación explícita para la propiedad `P` o el método `P`, o ambos, para evitar un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="b20bc-115">To implement both interfaces, a class has to use explicit implementation either for the property `P`, or the method `P`, or both, to avoid a compiler error.</span></span> <span data-ttu-id="b20bc-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b20bc-116">For example:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#NameCollision)]

<span data-ttu-id="b20bc-117">Si una clase hereda una implementación de método de una interfaz, ese método solo es accesible a través de una referencia del tipo de interfaz.</span><span class="sxs-lookup"><span data-stu-id="b20bc-117">If a class inherits a method implementation from an interface, that method is only accessible through a reference of the interface type.</span></span> <span data-ttu-id="b20bc-118">El miembro heredado no aparece como parte de la interfaz pública.</span><span class="sxs-lookup"><span data-stu-id="b20bc-118">The inherited member doesn't appear as part of the public interface.</span></span> <span data-ttu-id="b20bc-119">En el ejemplo siguiente se define una implementación predeterminada para un método de interfaz:</span><span class="sxs-lookup"><span data-stu-id="b20bc-119">The following sample defines a default implementation for an interface method:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefaultImplementation)]

<span data-ttu-id="b20bc-120">En el ejemplo siguiente se invoca la implementación predeterminada:</span><span class="sxs-lookup"><span data-stu-id="b20bc-120">The following sample invokes the default implementation:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallDefaultImplementation)]

<span data-ttu-id="b20bc-121">Cualquier clase que implemente la interfaz `IControl` puede invalidar el método `Paint` predeterminado, ya sea como un método público, o bien como una implementación de interfaz explícita.</span><span class="sxs-lookup"><span data-stu-id="b20bc-121">Any class that implements the `IControl` interface can override the default `Paint` method, either as a public method, or as an explicit interface implementation.</span></span>

## <a name="see-also"></a><span data-ttu-id="b20bc-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="b20bc-122">See also</span></span>

- [<span data-ttu-id="b20bc-123">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="b20bc-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b20bc-124">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="b20bc-124">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="b20bc-125">Interfaces</span><span class="sxs-lookup"><span data-stu-id="b20bc-125">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="b20bc-126">Herencia</span><span class="sxs-lookup"><span data-stu-id="b20bc-126">Inheritance</span></span>](../classes-and-structs/inheritance.md)
