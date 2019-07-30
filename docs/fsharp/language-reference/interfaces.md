---
title: Interfaces
description: Obtenga información F# sobre cómo las interfaces especifican conjuntos de miembros relacionados que otras clases implementan.
ms.date: 05/16/2016
ms.openlocfilehash: 8f054a668ad0fbc2453a45883e8052471280eca3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627651"
---
# <a name="interfaces"></a><span data-ttu-id="d5df5-103">Interfaces</span><span class="sxs-lookup"><span data-stu-id="d5df5-103">Interfaces</span></span>

<span data-ttu-id="d5df5-104">Las *interfaces* especifican conjuntos de miembros relacionados que otras clases implementan.</span><span class="sxs-lookup"><span data-stu-id="d5df5-104">*Interfaces* specify sets of related members that other classes implement.</span></span>

## <a name="syntax"></a><span data-ttu-id="d5df5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5df5-105">Syntax</span></span>

```fsharp
// Interface declaration:
[ attributes ]
type [accessibility-modifier] interface-name =
    [ interface ]     [ inherit base-interface-name ...]
    abstract member1 : [ argument-types1 -> ] return-type1
    abstract member2 : [ argument-types2 -> ] return-type2
    ...
[ end ]

// Implementing, inside a class type definition:
interface interface-name with
    member self-identifier.member1argument-list = method-body1
    member self-identifier.member2argument-list = method-body2

// Implementing, by using an object expression:
[ attributes ]
let class-name (argument-list) =
    { new interface-name with
        member self-identifier.member1argument-list = method-body1
        member self-identifier.member2argument-list = method-body2
        [ base-interface-definitions ]
    }
    member-list
```

## <a name="remarks"></a><span data-ttu-id="d5df5-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d5df5-106">Remarks</span></span>

<span data-ttu-id="d5df5-107">Las declaraciones de interfaz son similares a las declaraciones de clase, salvo que no se implementa ningún miembro.</span><span class="sxs-lookup"><span data-stu-id="d5df5-107">Interface declarations resemble class declarations except that no members are implemented.</span></span> <span data-ttu-id="d5df5-108">En su lugar, todos los miembros son abstractos, como se indica `abstract`en la palabra clave.</span><span class="sxs-lookup"><span data-stu-id="d5df5-108">Instead, all the members are abstract, as indicated by the keyword `abstract`.</span></span> <span data-ttu-id="d5df5-109">No se proporciona un cuerpo de método para los métodos abstractos.</span><span class="sxs-lookup"><span data-stu-id="d5df5-109">You do not provide a method body for abstract methods.</span></span> <span data-ttu-id="d5df5-110">Sin embargo, puede proporcionar una implementación predeterminada al incluir también una definición independiente del miembro como un método junto con la `default` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="d5df5-110">However, you can provide a default implementation by also including a separate definition of the member as a method together with the `default` keyword.</span></span> <span data-ttu-id="d5df5-111">Hacerlo es equivalente a crear un método virtual en una clase base en otros lenguajes .NET.</span><span class="sxs-lookup"><span data-stu-id="d5df5-111">Doing so is equivalent to creating a virtual method in a base class in other .NET languages.</span></span> <span data-ttu-id="d5df5-112">Este tipo de método virtual se puede invalidar en las clases que implementan la interfaz.</span><span class="sxs-lookup"><span data-stu-id="d5df5-112">Such a virtual method can be overridden in classes that implement the interface.</span></span>

<span data-ttu-id="d5df5-113">La accesibilidad predeterminada para las interfaces `public`es.</span><span class="sxs-lookup"><span data-stu-id="d5df5-113">The default accessibility for interfaces is `public`.</span></span>

<span data-ttu-id="d5df5-114">Opcionalmente, puede asignar un nombre a cada parámetro de método F# usando la sintaxis normal:</span><span class="sxs-lookup"><span data-stu-id="d5df5-114">You can optionally give each method parameter a name using normal F# syntax:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

<span data-ttu-id="d5df5-115">En el ejemplo `ISprintable` anterior, el `Print` método tiene un único parámetro del tipo `string` con el nombre `format`.</span><span class="sxs-lookup"><span data-stu-id="d5df5-115">In the above `ISprintable` example, the `Print` method has a single parameter of the type `string` with the name `format`.</span></span>

<span data-ttu-id="d5df5-116">Hay dos maneras de implementar interfaces: mediante el uso de expresiones de objeto y el uso de tipos de clase.</span><span class="sxs-lookup"><span data-stu-id="d5df5-116">There are two ways to implement interfaces: by using object expressions, and by using class types.</span></span> <span data-ttu-id="d5df5-117">En cualquier caso, el tipo de clase o la expresión de objeto proporciona cuerpos de método para los métodos abstractos de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="d5df5-117">In either case, the class type or object expression provides method bodies for abstract methods of the interface.</span></span> <span data-ttu-id="d5df5-118">Las implementaciones son específicas de cada tipo que implementa la interfaz.</span><span class="sxs-lookup"><span data-stu-id="d5df5-118">Implementations are specific to each type that implements the interface.</span></span> <span data-ttu-id="d5df5-119">Por lo tanto, los métodos de interfaz en tipos diferentes pueden ser diferentes entre sí.</span><span class="sxs-lookup"><span data-stu-id="d5df5-119">Therefore, interface methods on different types might be different from each other.</span></span>

<span data-ttu-id="d5df5-120">Las palabras `interface` clave `end`y, que marcan el inicio y el final de la definición, son opcionales cuando se usa la sintaxis ligera.</span><span class="sxs-lookup"><span data-stu-id="d5df5-120">The keywords `interface` and `end`, which mark the start and end of the definition, are optional when you use lightweight syntax.</span></span> <span data-ttu-id="d5df5-121">Si no usa estas palabras clave, el compilador intenta deducir si el tipo es una clase o una interfaz mediante el análisis de las construcciones que se usan.</span><span class="sxs-lookup"><span data-stu-id="d5df5-121">If you do not use these keywords, the compiler attempts to infer whether the type is a class or an interface by analyzing the constructs that you use.</span></span> <span data-ttu-id="d5df5-122">Si define un miembro o usa otra sintaxis de clase, el tipo se interpreta como una clase.</span><span class="sxs-lookup"><span data-stu-id="d5df5-122">If you define a member or use other class syntax, the type is interpreted as a class.</span></span>

<span data-ttu-id="d5df5-123">El estilo de codificación de .NET consiste en comenzar todas las interfaces `I`con una letra mayúscula.</span><span class="sxs-lookup"><span data-stu-id="d5df5-123">The .NET coding style is to begin all interfaces with a capital `I`.</span></span>

## <a name="implementing-interfaces-by-using-class-types"></a><span data-ttu-id="d5df5-124">Implementar interfaces mediante tipos de clase</span><span class="sxs-lookup"><span data-stu-id="d5df5-124">Implementing Interfaces by Using Class Types</span></span>

<span data-ttu-id="d5df5-125">Puede implementar una o más interfaces en un tipo de clase mediante la `interface` palabra clave, el nombre de la interfaz y la `with` palabra clave, seguida de las definiciones de miembro de interfaz, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="d5df5-125">You can implement one or more interfaces in a class type by using the `interface` keyword, the name of the interface, and the `with` keyword, followed by the interface member definitions, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

<span data-ttu-id="d5df5-126">Las implementaciones de interfaz se heredan, por lo que las clases derivadas no necesitan volver a implementarlas.</span><span class="sxs-lookup"><span data-stu-id="d5df5-126">Interface implementations are inherited, so any derived classes do not need to reimplement them.</span></span>

## <a name="calling-interface-methods"></a><span data-ttu-id="d5df5-127">Llamar a métodos de interfaz</span><span class="sxs-lookup"><span data-stu-id="d5df5-127">Calling Interface Methods</span></span>

<span data-ttu-id="d5df5-128">Solo se puede llamar a los métodos de interfaz a través de la interfaz, no a través de ningún objeto del tipo que implementa la interfaz.</span><span class="sxs-lookup"><span data-stu-id="d5df5-128">Interface methods can be called only through the interface, not through any object of the type that implements the interface.</span></span> <span data-ttu-id="d5df5-129">Por lo tanto, es posible que tenga que convertir al tipo de interfaz mediante `:>` el operador o `upcast` el operador para llamar a estos métodos.</span><span class="sxs-lookup"><span data-stu-id="d5df5-129">Thus, you might have to upcast to the interface type by using the `:>` operator or the `upcast` operator in order to call these methods.</span></span>

<span data-ttu-id="d5df5-130">Para llamar al método de interfaz cuando tiene un objeto de tipo `SomeClass`, debe convertir el objeto al tipo de interfaz, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="d5df5-130">To call the interface method when you have an object of type `SomeClass`, you must upcast the object to the interface type, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

<span data-ttu-id="d5df5-131">Una alternativa consiste en declarar un método en el objeto que convierte y llama al método de interfaz, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d5df5-131">An alternative is to declare a method on the object that upcasts and calls the interface method, as in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]

## <a name="implementing-interfaces-by-using-object-expressions"></a><span data-ttu-id="d5df5-132">Implementar interfaces mediante expresiones de objeto</span><span class="sxs-lookup"><span data-stu-id="d5df5-132">Implementing Interfaces by Using Object Expressions</span></span>

<span data-ttu-id="d5df5-133">Las expresiones de objeto proporcionan una manera breve de implementar una interfaz.</span><span class="sxs-lookup"><span data-stu-id="d5df5-133">Object expressions provide a short way to implement an interface.</span></span> <span data-ttu-id="d5df5-134">Son útiles cuando no es necesario crear un tipo con nombre y simplemente se desea un objeto que admita los métodos de interfaz, sin ningún método adicional.</span><span class="sxs-lookup"><span data-stu-id="d5df5-134">They are useful when you do not have to create a named type, and you just want an object that supports the interface methods, without any additional methods.</span></span> <span data-ttu-id="d5df5-135">En el código siguiente se muestra una expresión de objeto.</span><span class="sxs-lookup"><span data-stu-id="d5df5-135">An object expression is illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]

## <a name="interface-inheritance"></a><span data-ttu-id="d5df5-136">Herencia de interfaz</span><span class="sxs-lookup"><span data-stu-id="d5df5-136">Interface Inheritance</span></span>

<span data-ttu-id="d5df5-137">Las interfaces pueden heredar de una o varias interfaces base.</span><span class="sxs-lookup"><span data-stu-id="d5df5-137">Interfaces can inherit from one or more base interfaces.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]

## <a name="see-also"></a><span data-ttu-id="d5df5-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5df5-138">See also</span></span>

- [<span data-ttu-id="d5df5-139">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="d5df5-139">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="d5df5-140">Expresiones de objeto</span><span class="sxs-lookup"><span data-stu-id="d5df5-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="d5df5-141">Clases</span><span class="sxs-lookup"><span data-stu-id="d5df5-141">Classes</span></span>](classes.md)
