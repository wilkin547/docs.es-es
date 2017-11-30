---
title: Interfaces (F#)
description: "Obtenga información acerca de cómo F # Interfaces especificar conjuntos de miembros relacionados que otras clases implementan."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3a082459-17d4-45cf-9153-0b7550a154ec
ms.openlocfilehash: d7c95e5f5cc0bc6c7f6393af990427ac491c5b79
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="interfaces"></a><span data-ttu-id="a2424-104">Interfaces</span><span class="sxs-lookup"><span data-stu-id="a2424-104">Interfaces</span></span>

<span data-ttu-id="a2424-105">*Interfaces* especificar conjuntos de miembros relacionados que otras clases implementan.</span><span class="sxs-lookup"><span data-stu-id="a2424-105">*Interfaces* specify sets of related members that other classes implement.</span></span>

## <a name="syntax"></a><span data-ttu-id="a2424-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a2424-106">Syntax</span></span>

```fsharp
// Interface declaration:
[ attributes ]
type interface-name =
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

## <a name="remarks"></a><span data-ttu-id="a2424-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a2424-107">Remarks</span></span>
<span data-ttu-id="a2424-108">Declaraciones de interfaz son similares a las declaraciones de clase, salvo que no se implementa ningún miembro.</span><span class="sxs-lookup"><span data-stu-id="a2424-108">Interface declarations resemble class declarations except that no members are implemented.</span></span> <span data-ttu-id="a2424-109">En su lugar, todos los miembros son abstractos, tal como se indica mediante la palabra clave `abstract`.</span><span class="sxs-lookup"><span data-stu-id="a2424-109">Instead, all the members are abstract, as indicated by the keyword `abstract`.</span></span> <span data-ttu-id="a2424-110">No se proporciona un cuerpo de método para los métodos abstractos.</span><span class="sxs-lookup"><span data-stu-id="a2424-110">You do not provide a method body for abstract methods.</span></span> <span data-ttu-id="a2424-111">Sin embargo, puede proporcionar una implementación predeterminada también incluye una definición independiente del miembro como método junto con el `default` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="a2424-111">However, you can provide a default implementation by also including a separate definition of the member as a method together with the `default` keyword.</span></span> <span data-ttu-id="a2424-112">Esto es equivalente a la creación de un método virtual en una clase base en otros lenguajes. NET.</span><span class="sxs-lookup"><span data-stu-id="a2424-112">Doing so is equivalent to creating a virtual method in a base class in other .NET languages.</span></span> <span data-ttu-id="a2424-113">Este tipo de método virtual puede reemplazarse en las clases que implementan la interfaz.</span><span class="sxs-lookup"><span data-stu-id="a2424-113">Such a virtual method can be overridden in classes that implement the interface.</span></span>

<span data-ttu-id="a2424-114">También puede asignar a cada parámetro de método un nombre que se usa la sintaxis normal de F #:</span><span class="sxs-lookup"><span data-stu-id="a2424-114">You can optionally give each method parameter a name using normal F# syntax:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

<span data-ttu-id="a2424-115">En los pasos anteriores `ISprintable` ejemplo, el `Print` método tiene un único parámetro del tipo `string` con el nombre `format`.</span><span class="sxs-lookup"><span data-stu-id="a2424-115">In the above `ISprintable` example, the `Print` method has a single parameter of the type `string` with the name `format`.</span></span>

<span data-ttu-id="a2424-116">Hay dos maneras de implementar interfaces: mediante expresiones de objeto y mediante el uso de tipos de clase.</span><span class="sxs-lookup"><span data-stu-id="a2424-116">There are two ways to implement interfaces: by using object expressions, and by using class types.</span></span> <span data-ttu-id="a2424-117">En cualquier caso, la expresión de tipo u objeto de clase proporciona cuerpos de método para los métodos abstractos de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="a2424-117">In either case, the class type or object expression provides method bodies for abstract methods of the interface.</span></span> <span data-ttu-id="a2424-118">Las implementaciones son específicas para cada tipo que implementa la interfaz.</span><span class="sxs-lookup"><span data-stu-id="a2424-118">Implementations are specific to each type that implements the interface.</span></span> <span data-ttu-id="a2424-119">Por lo tanto, los métodos de interfaz en diferentes tipos puede variar entre sí.</span><span class="sxs-lookup"><span data-stu-id="a2424-119">Therefore, interface methods on different types might be different from each other.</span></span>

<span data-ttu-id="a2424-120">Las palabras clave `interface` y `end`, que marca el inicio y el final de la definición, son opcionales cuando emplee la sintaxis ligera.</span><span class="sxs-lookup"><span data-stu-id="a2424-120">The keywords `interface` and `end`, which mark the start and end of the definition, are optional when you use lightweight syntax.</span></span> <span data-ttu-id="a2424-121">Si no utiliza estas palabras clave, el compilador intenta deducir si el tipo es una clase o una interfaz analizando las construcciones que usan.</span><span class="sxs-lookup"><span data-stu-id="a2424-121">If you do not use these keywords, the compiler attempts to infer whether the type is a class or an interface by analyzing the constructs that you use.</span></span> <span data-ttu-id="a2424-122">Si se define un miembro o utilizar otra sintaxis de clase, el tipo se interpreta como una clase.</span><span class="sxs-lookup"><span data-stu-id="a2424-122">If you define a member or use other class syntax, the type is interpreted as a class.</span></span>

<span data-ttu-id="a2424-123">El estilo de codificación de .NET consiste en empezar a todas las interfaces con una letra mayúscula `I`.</span><span class="sxs-lookup"><span data-stu-id="a2424-123">The .NET coding style is to begin all interfaces with a capital `I`.</span></span>


## <a name="implementing-interfaces-by-using-class-types"></a><span data-ttu-id="a2424-124">Implementar Interfaces mediante tipos de clase</span><span class="sxs-lookup"><span data-stu-id="a2424-124">Implementing Interfaces by Using Class Types</span></span>
<span data-ttu-id="a2424-125">Puede implementar una o varias interfaces en un tipo de clase mediante el `interface` palabra clave, el nombre de la interfaz y la `with` (palabra clave), seguido de las definiciones de miembro de interfaz, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a2424-125">You can implement one or more interfaces in a class type by using the `interface` keyword, the name of the interface, and the `with` keyword, followed by the interface member definitions, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

<span data-ttu-id="a2424-126">Implementaciones de interfaz se heredan, por lo que no es necesario que las clases derivadas implementarlas.</span><span class="sxs-lookup"><span data-stu-id="a2424-126">Interface implementations are inherited, so any derived classes do not need to reimplement them.</span></span>


## <a name="calling-interface-methods"></a><span data-ttu-id="a2424-127">Llamar a métodos de interfaz</span><span class="sxs-lookup"><span data-stu-id="a2424-127">Calling Interface Methods</span></span>
<span data-ttu-id="a2424-128">Pueden llamar a métodos de interfaz sólo a través de la interfaz, no a través de cualquier objeto del tipo que implementa la interfaz.</span><span class="sxs-lookup"><span data-stu-id="a2424-128">Interface methods can be called only through the interface, not through any object of the type that implements the interface.</span></span> <span data-ttu-id="a2424-129">Por lo tanto, es posible que deba conversión hacia arriba para el tipo de interfaz mediante el uso de la `:>` operador o la `upcast` operador para poder llamar a estos métodos.</span><span class="sxs-lookup"><span data-stu-id="a2424-129">Thus, you might have to upcast to the interface type by using the `:>` operator or the `upcast` operator in order to call these methods.</span></span>

<span data-ttu-id="a2424-130">Para llamar al método de interfaz cuando se tiene un objeto de tipo `SomeClass`, debe conversión hacia arriba el objeto al tipo de interfaz, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a2424-130">To call the interface method when you have an object of type `SomeClass`, you must upcast the object to the interface type, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

<span data-ttu-id="a2424-131">Una alternativa consiste en declarar un método en el objeto que convierte y llama al método de interfaz, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a2424-131">An alternative is to declare a method on the object that upcasts and calls the interface method, as in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]
    
## <a name="implementing-interfaces-by-using-object-expressions"></a><span data-ttu-id="a2424-132">Implementar Interfaces mediante expresiones de objeto</span><span class="sxs-lookup"><span data-stu-id="a2424-132">Implementing Interfaces by Using Object Expressions</span></span>
<span data-ttu-id="a2424-133">Expresiones de objeto proporcionan una manera abreviada para implementar una interfaz.</span><span class="sxs-lookup"><span data-stu-id="a2424-133">Object expressions provide a short way to implement an interface.</span></span> <span data-ttu-id="a2424-134">Son útiles cuando no tienes que volver a crear un tipo con nombre y su intención es un objeto que es compatible con los métodos de interfaz, sin ningún método adicional.</span><span class="sxs-lookup"><span data-stu-id="a2424-134">They are useful when you do not have to create a named type, and you just want an object that supports the interface methods, without any additional methods.</span></span> <span data-ttu-id="a2424-135">Una expresión de objeto se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a2424-135">An object expression is illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]
    
## <a name="interface-inheritance"></a><span data-ttu-id="a2424-136">Herencia de interfaz</span><span class="sxs-lookup"><span data-stu-id="a2424-136">Interface Inheritance</span></span>
<span data-ttu-id="a2424-137">Interfaces pueden heredar de una o más interfaces base.</span><span class="sxs-lookup"><span data-stu-id="a2424-137">Interfaces can inherit from one or more base interfaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]
    
## <a name="see-also"></a><span data-ttu-id="a2424-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2424-138">See Also</span></span>
[<span data-ttu-id="a2424-139">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="a2424-139">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="a2424-140">Expresiones de objeto</span><span class="sxs-lookup"><span data-stu-id="a2424-140">Object Expressions</span></span>](object-expressions.md)

[<span data-ttu-id="a2424-141">Clases</span><span class="sxs-lookup"><span data-stu-id="a2424-141">Classes</span></span>](classes.md)
