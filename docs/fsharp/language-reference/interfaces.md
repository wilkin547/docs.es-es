---
title: Interfaces
description: Obtenga información sobre cómo F# Interfaces especifican conjuntos de miembros relacionados que otras clases implementan.
ms.date: 05/16/2016
ms.openlocfilehash: 5b57769af6c05b83b3a112635033abf4efaca772
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645372"
---
# <a name="interfaces"></a><span data-ttu-id="12936-103">Interfaces</span><span class="sxs-lookup"><span data-stu-id="12936-103">Interfaces</span></span>

<span data-ttu-id="12936-104">*Interfaces* especificar conjuntos de miembros relacionados que otras clases implementan.</span><span class="sxs-lookup"><span data-stu-id="12936-104">*Interfaces* specify sets of related members that other classes implement.</span></span>

## <a name="syntax"></a><span data-ttu-id="12936-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="12936-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="12936-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="12936-106">Remarks</span></span>

<span data-ttu-id="12936-107">Declaraciones de interfaz son similares a las declaraciones de clase, salvo que no implementan miembros.</span><span class="sxs-lookup"><span data-stu-id="12936-107">Interface declarations resemble class declarations except that no members are implemented.</span></span> <span data-ttu-id="12936-108">En su lugar, todos los miembros son abstractos, tal como se indica mediante la palabra clave `abstract`.</span><span class="sxs-lookup"><span data-stu-id="12936-108">Instead, all the members are abstract, as indicated by the keyword `abstract`.</span></span> <span data-ttu-id="12936-109">No se proporcionan un cuerpo de método para los métodos abstractos.</span><span class="sxs-lookup"><span data-stu-id="12936-109">You do not provide a method body for abstract methods.</span></span> <span data-ttu-id="12936-110">Sin embargo, puede proporcionar una implementación predeterminada también incluyendo una definición independiente del miembro como un método junto con el `default` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="12936-110">However, you can provide a default implementation by also including a separate definition of the member as a method together with the `default` keyword.</span></span> <span data-ttu-id="12936-111">Si lo hace, es equivalente a la creación de un método virtual en una clase base en otros lenguajes. NET.</span><span class="sxs-lookup"><span data-stu-id="12936-111">Doing so is equivalent to creating a virtual method in a base class in other .NET languages.</span></span> <span data-ttu-id="12936-112">Este tipo de método virtual se puede invalidar en clases que implementan la interfaz.</span><span class="sxs-lookup"><span data-stu-id="12936-112">Such a virtual method can be overridden in classes that implement the interface.</span></span>

<span data-ttu-id="12936-113">La accesibilidad predeterminada para las interfaces es `public`.</span><span class="sxs-lookup"><span data-stu-id="12936-113">The default accessibility for interfaces is `public`.</span></span>

<span data-ttu-id="12936-114">Cada parámetro del método si lo desea puede asignarle un nombre con normal F# sintaxis:</span><span class="sxs-lookup"><span data-stu-id="12936-114">You can optionally give each method parameter a name using normal F# syntax:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

<span data-ttu-id="12936-115">En la fórmula anterior `ISprintable` ejemplo, el `Print` método tiene un parámetro único del tipo `string` con el nombre `format`.</span><span class="sxs-lookup"><span data-stu-id="12936-115">In the above `ISprintable` example, the `Print` method has a single parameter of the type `string` with the name `format`.</span></span>

<span data-ttu-id="12936-116">Hay dos maneras de implementar interfaces: mediante el uso de expresiones de objeto y mediante el uso de tipos de clase.</span><span class="sxs-lookup"><span data-stu-id="12936-116">There are two ways to implement interfaces: by using object expressions, and by using class types.</span></span> <span data-ttu-id="12936-117">En cualquier caso, la expresión de tipo u objeto de clase proporciona los cuerpos de método para los métodos abstractos de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="12936-117">In either case, the class type or object expression provides method bodies for abstract methods of the interface.</span></span> <span data-ttu-id="12936-118">Las implementaciones son específicas de cada tipo que implementa la interfaz.</span><span class="sxs-lookup"><span data-stu-id="12936-118">Implementations are specific to each type that implements the interface.</span></span> <span data-ttu-id="12936-119">Por lo tanto, los métodos de interfaz en diferentes tipos pueden variar entre sí.</span><span class="sxs-lookup"><span data-stu-id="12936-119">Therefore, interface methods on different types might be different from each other.</span></span>

<span data-ttu-id="12936-120">Las palabras clave `interface` y `end`, que marca el inicio y finalización de la definición, son opcionales cuando se usa la sintaxis ligera.</span><span class="sxs-lookup"><span data-stu-id="12936-120">The keywords `interface` and `end`, which mark the start and end of the definition, are optional when you use lightweight syntax.</span></span> <span data-ttu-id="12936-121">Si no utiliza estas palabras clave, el compilador intenta deducir si el tipo es una clase o una interfaz mediante el análisis de las construcciones que usan.</span><span class="sxs-lookup"><span data-stu-id="12936-121">If you do not use these keywords, the compiler attempts to infer whether the type is a class or an interface by analyzing the constructs that you use.</span></span> <span data-ttu-id="12936-122">Si se define un miembro o usar otras sintaxis de la clase, el tipo se interpreta como una clase.</span><span class="sxs-lookup"><span data-stu-id="12936-122">If you define a member or use other class syntax, the type is interpreted as a class.</span></span>

<span data-ttu-id="12936-123">El estilo de codificación de .NET consiste en empezar a todas las interfaces con una letra mayúscula `I`.</span><span class="sxs-lookup"><span data-stu-id="12936-123">The .NET coding style is to begin all interfaces with a capital `I`.</span></span>

## <a name="implementing-interfaces-by-using-class-types"></a><span data-ttu-id="12936-124">Implementar Interfaces mediante tipos de clase</span><span class="sxs-lookup"><span data-stu-id="12936-124">Implementing Interfaces by Using Class Types</span></span>

<span data-ttu-id="12936-125">Puede implementar una o varias interfaces en un tipo de clase mediante el `interface` palabra clave, el nombre de la interfaz y el `with` palabra clave, seguida de las definiciones de miembro de interfaz, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="12936-125">You can implement one or more interfaces in a class type by using the `interface` keyword, the name of the interface, and the `with` keyword, followed by the interface member definitions, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

<span data-ttu-id="12936-126">Implementaciones de interfaz se heredan, por lo que cualquier clase derivada no es necesario volver a implementar en ellos.</span><span class="sxs-lookup"><span data-stu-id="12936-126">Interface implementations are inherited, so any derived classes do not need to reimplement them.</span></span>

## <a name="calling-interface-methods"></a><span data-ttu-id="12936-127">Llamar a métodos de interfaz</span><span class="sxs-lookup"><span data-stu-id="12936-127">Calling Interface Methods</span></span>

<span data-ttu-id="12936-128">Los métodos de interfaz se pueden llamar solo a través de la interfaz, no a través de cualquier objeto del tipo que implementa la interfaz.</span><span class="sxs-lookup"><span data-stu-id="12936-128">Interface methods can be called only through the interface, not through any object of the type that implements the interface.</span></span> <span data-ttu-id="12936-129">Por lo tanto, es posible que deba conversión hacia arriba en el tipo de interfaz mediante el uso de la `:>` operador o la `upcast` operador para poder llamar a estos métodos.</span><span class="sxs-lookup"><span data-stu-id="12936-129">Thus, you might have to upcast to the interface type by using the `:>` operator or the `upcast` operator in order to call these methods.</span></span>

<span data-ttu-id="12936-130">Para llamar al método de interfaz cuando tenga un objeto de tipo `SomeClass`, debe upcast el objeto al tipo de interfaz, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="12936-130">To call the interface method when you have an object of type `SomeClass`, you must upcast the object to the interface type, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

<span data-ttu-id="12936-131">Una alternativa consiste en declarar un método en el objeto que convierte y llama al método de interfaz, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="12936-131">An alternative is to declare a method on the object that upcasts and calls the interface method, as in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]

## <a name="implementing-interfaces-by-using-object-expressions"></a><span data-ttu-id="12936-132">Implementar Interfaces mediante expresiones de objeto</span><span class="sxs-lookup"><span data-stu-id="12936-132">Implementing Interfaces by Using Object Expressions</span></span>

<span data-ttu-id="12936-133">Expresiones de objeto proporcionan una forma rápida para implementar una interfaz.</span><span class="sxs-lookup"><span data-stu-id="12936-133">Object expressions provide a short way to implement an interface.</span></span> <span data-ttu-id="12936-134">Son útiles cuando no es necesario que crear un tipo con nombre, y tan solo quiere un objeto que admite los métodos de interfaz sin métodos adicionales.</span><span class="sxs-lookup"><span data-stu-id="12936-134">They are useful when you do not have to create a named type, and you just want an object that supports the interface methods, without any additional methods.</span></span> <span data-ttu-id="12936-135">Una expresión de objeto se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="12936-135">An object expression is illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]

## <a name="interface-inheritance"></a><span data-ttu-id="12936-136">Herencia de interfaz</span><span class="sxs-lookup"><span data-stu-id="12936-136">Interface Inheritance</span></span>

<span data-ttu-id="12936-137">Interfaces pueden heredar de una o varias interfaces bases.</span><span class="sxs-lookup"><span data-stu-id="12936-137">Interfaces can inherit from one or more base interfaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]

## <a name="see-also"></a><span data-ttu-id="12936-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="12936-138">See also</span></span>

- [<span data-ttu-id="12936-139">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="12936-139">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="12936-140">Expresiones de objeto</span><span class="sxs-lookup"><span data-stu-id="12936-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="12936-141">Clases</span><span class="sxs-lookup"><span data-stu-id="12936-141">Classes</span></span>](classes.md)
