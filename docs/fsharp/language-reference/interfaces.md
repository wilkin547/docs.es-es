---
title: Interfaces
description: 'Obtenga información sobre cómo las interfaces de F # especifican conjuntos de miembros relacionados que otras clases implementan.'
ms.date: 08/15/2020
ms.openlocfilehash: 0cef2932045dae401f5aa069107815543457ca4a
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2020
ms.locfileid: "94557056"
---
# <a name="interfaces"></a><span data-ttu-id="c6901-103">Interfaces</span><span class="sxs-lookup"><span data-stu-id="c6901-103">Interfaces</span></span>

<span data-ttu-id="c6901-104">Las *interfaces* especifican conjuntos de miembros relacionados que otras clases implementan.</span><span class="sxs-lookup"><span data-stu-id="c6901-104">*Interfaces* specify sets of related members that other classes implement.</span></span>

## <a name="syntax"></a><span data-ttu-id="c6901-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c6901-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="c6901-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c6901-106">Remarks</span></span>

<span data-ttu-id="c6901-107">Las declaraciones de interfaz son similares a las declaraciones de clase, salvo que no se implementa ningún miembro.</span><span class="sxs-lookup"><span data-stu-id="c6901-107">Interface declarations resemble class declarations except that no members are implemented.</span></span> <span data-ttu-id="c6901-108">En su lugar, todos los miembros son abstractos, como se indica en la palabra clave `abstract` .</span><span class="sxs-lookup"><span data-stu-id="c6901-108">Instead, all the members are abstract, as indicated by the keyword `abstract`.</span></span> <span data-ttu-id="c6901-109">No se proporciona un cuerpo de método para los métodos abstractos.</span><span class="sxs-lookup"><span data-stu-id="c6901-109">You do not provide a method body for abstract methods.</span></span> <span data-ttu-id="c6901-110">Sin embargo, puede proporcionar una implementación predeterminada al incluir también una definición independiente del miembro como un método junto con la `default` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="c6901-110">However, you can provide a default implementation by also including a separate definition of the member as a method together with the `default` keyword.</span></span> <span data-ttu-id="c6901-111">Hacerlo es equivalente a crear un método virtual en una clase base en otros lenguajes .NET.</span><span class="sxs-lookup"><span data-stu-id="c6901-111">Doing so is equivalent to creating a virtual method in a base class in other .NET languages.</span></span> <span data-ttu-id="c6901-112">Este tipo de método virtual se puede invalidar en las clases que implementan la interfaz.</span><span class="sxs-lookup"><span data-stu-id="c6901-112">Such a virtual method can be overridden in classes that implement the interface.</span></span>

<span data-ttu-id="c6901-113">La accesibilidad predeterminada para las interfaces es `public` .</span><span class="sxs-lookup"><span data-stu-id="c6901-113">The default accessibility for interfaces is `public`.</span></span>

<span data-ttu-id="c6901-114">Opcionalmente, puede asignar un nombre a cada parámetro de método mediante la sintaxis de F # normal:</span><span class="sxs-lookup"><span data-stu-id="c6901-114">You can optionally give each method parameter a name using normal F# syntax:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

<span data-ttu-id="c6901-115">En el `ISprintable` ejemplo anterior, el `Print` método tiene un único parámetro del tipo `string` con el nombre `format` .</span><span class="sxs-lookup"><span data-stu-id="c6901-115">In the above `ISprintable` example, the `Print` method has a single parameter of the type `string` with the name `format`.</span></span>

<span data-ttu-id="c6901-116">Hay dos maneras de implementar interfaces: mediante el uso de expresiones de objeto y el uso de tipos de clase.</span><span class="sxs-lookup"><span data-stu-id="c6901-116">There are two ways to implement interfaces: by using object expressions, and by using class types.</span></span> <span data-ttu-id="c6901-117">En cualquier caso, el tipo de clase o la expresión de objeto proporciona cuerpos de método para los métodos abstractos de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="c6901-117">In either case, the class type or object expression provides method bodies for abstract methods of the interface.</span></span> <span data-ttu-id="c6901-118">Las implementaciones son específicas de cada tipo que implementa la interfaz.</span><span class="sxs-lookup"><span data-stu-id="c6901-118">Implementations are specific to each type that implements the interface.</span></span> <span data-ttu-id="c6901-119">Por lo tanto, los métodos de interfaz en tipos diferentes pueden ser diferentes entre sí.</span><span class="sxs-lookup"><span data-stu-id="c6901-119">Therefore, interface methods on different types might be different from each other.</span></span>

<span data-ttu-id="c6901-120">Las palabras clave `interface` y `end` , que marcan el inicio y el final de la definición, son opcionales cuando se usa la sintaxis ligera.</span><span class="sxs-lookup"><span data-stu-id="c6901-120">The keywords `interface` and `end`, which mark the start and end of the definition, are optional when you use lightweight syntax.</span></span> <span data-ttu-id="c6901-121">Si no usa estas palabras clave, el compilador intenta deducir si el tipo es una clase o una interfaz mediante el análisis de las construcciones que se usan.</span><span class="sxs-lookup"><span data-stu-id="c6901-121">If you do not use these keywords, the compiler attempts to infer whether the type is a class or an interface by analyzing the constructs that you use.</span></span> <span data-ttu-id="c6901-122">Si define un miembro o usa otra sintaxis de clase, el tipo se interpreta como una clase.</span><span class="sxs-lookup"><span data-stu-id="c6901-122">If you define a member or use other class syntax, the type is interpreted as a class.</span></span>

<span data-ttu-id="c6901-123">El estilo de codificación de .NET consiste en comenzar todas las interfaces con una letra mayúscula `I` .</span><span class="sxs-lookup"><span data-stu-id="c6901-123">The .NET coding style is to begin all interfaces with a capital `I`.</span></span>

<span data-ttu-id="c6901-124">Puede especificar varios parámetros de dos maneras: F #-Style y. Estilo de red.</span><span class="sxs-lookup"><span data-stu-id="c6901-124">You can specify multiple parameters in two ways: F#-style and .NET-style.</span></span> <span data-ttu-id="c6901-125">Ambos se compilarán de la misma manera para los consumidores de .NET, pero F #-Style forzará a los autores de llamadas de F # a usar la aplicación de parámetros de estilo F # y. El estilo de red obliga a los autores de llamadas de F # a usar la aplicación de argumentos de tupla.</span><span class="sxs-lookup"><span data-stu-id="c6901-125">Both will compile the same way for .NET consumers, but F#-style will force F# callers to use F#-style parameter application and .NET-style will force F# callers to use tupled argument application.</span></span>

```fsharp
type INumeric1 =
    abstract Add: x: int -> y: int -> int

type INumeric2 =
    abstract Add: x: int * y: int -> int
```

## <a name="implementing-interfaces-by-using-class-types"></a><span data-ttu-id="c6901-126">Implementar interfaces mediante tipos de clase</span><span class="sxs-lookup"><span data-stu-id="c6901-126">Implementing Interfaces by Using Class Types</span></span>

<span data-ttu-id="c6901-127">Puede implementar una o más interfaces en un tipo de clase mediante la `interface` palabra clave, el nombre de la interfaz y la `with` palabra clave, seguida de las definiciones de miembro de interfaz, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="c6901-127">You can implement one or more interfaces in a class type by using the `interface` keyword, the name of the interface, and the `with` keyword, followed by the interface member definitions, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

<span data-ttu-id="c6901-128">Las implementaciones de interfaz se heredan, por lo que las clases derivadas no necesitan volver a implementarlas.</span><span class="sxs-lookup"><span data-stu-id="c6901-128">Interface implementations are inherited, so any derived classes do not need to reimplement them.</span></span>

## <a name="calling-interface-methods"></a><span data-ttu-id="c6901-129">Llamar a métodos de interfaz</span><span class="sxs-lookup"><span data-stu-id="c6901-129">Calling Interface Methods</span></span>

<span data-ttu-id="c6901-130">Solo se puede llamar a los métodos de interfaz a través de la interfaz, no a través de ningún objeto del tipo que implementa la interfaz.</span><span class="sxs-lookup"><span data-stu-id="c6901-130">Interface methods can be called only through the interface, not through any object of the type that implements the interface.</span></span> <span data-ttu-id="c6901-131">Por lo tanto, es posible que tenga que convertir al tipo de interfaz mediante el `:>` operador o el `upcast` operador para llamar a estos métodos.</span><span class="sxs-lookup"><span data-stu-id="c6901-131">Thus, you might have to upcast to the interface type by using the `:>` operator or the `upcast` operator in order to call these methods.</span></span>

<span data-ttu-id="c6901-132">Para llamar al método de interfaz cuando tiene un objeto de tipo `SomeClass` , debe convertir el objeto al tipo de interfaz, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="c6901-132">To call the interface method when you have an object of type `SomeClass`, you must upcast the object to the interface type, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

<span data-ttu-id="c6901-133">Una alternativa consiste en declarar un método en el objeto que convierte y llama al método de interfaz, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c6901-133">An alternative is to declare a method on the object that upcasts and calls the interface method, as in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]

## <a name="implementing-interfaces-by-using-object-expressions"></a><span data-ttu-id="c6901-134">Implementar interfaces mediante expresiones de objeto</span><span class="sxs-lookup"><span data-stu-id="c6901-134">Implementing Interfaces by Using Object Expressions</span></span>

<span data-ttu-id="c6901-135">Las expresiones de objeto proporcionan una manera breve de implementar una interfaz.</span><span class="sxs-lookup"><span data-stu-id="c6901-135">Object expressions provide a short way to implement an interface.</span></span> <span data-ttu-id="c6901-136">Son útiles cuando no es necesario crear un tipo con nombre y simplemente se desea un objeto que admita los métodos de interfaz, sin ningún método adicional.</span><span class="sxs-lookup"><span data-stu-id="c6901-136">They are useful when you do not have to create a named type, and you just want an object that supports the interface methods, without any additional methods.</span></span> <span data-ttu-id="c6901-137">En el código siguiente se muestra una expresión de objeto.</span><span class="sxs-lookup"><span data-stu-id="c6901-137">An object expression is illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]

## <a name="interface-inheritance"></a><span data-ttu-id="c6901-138">Herencia de interfaz</span><span class="sxs-lookup"><span data-stu-id="c6901-138">Interface Inheritance</span></span>

<span data-ttu-id="c6901-139">Las interfaces pueden heredar de una o varias interfaces base.</span><span class="sxs-lookup"><span data-stu-id="c6901-139">Interfaces can inherit from one or more base interfaces.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]

## <a name="implementing-interfaces-with-default-implementations"></a><span data-ttu-id="c6901-140">Implementar interfaces con implementaciones predeterminadas</span><span class="sxs-lookup"><span data-stu-id="c6901-140">Implementing interfaces with default implementations</span></span>

<span data-ttu-id="c6901-141">C# admite la definición de interfaces con implementaciones predeterminadas, como:</span><span class="sxs-lookup"><span data-stu-id="c6901-141">C# supports defining interfaces with default implementations, like so:</span></span>

```csharp
using System;

namespace CSharp
{
    public interface MyDim
    {
        public int Z => 0;
    }
}
```

<span data-ttu-id="c6901-142">Se pueden utilizar directamente desde F #:</span><span class="sxs-lookup"><span data-stu-id="c6901-142">These are directly consumable from F#:</span></span>

```fsharp
open CSharp

// You can implement the interface via a class
type MyType() =
    member _.M() = ()

    interface MyDim

let md = MyType() :> MyDim
printfn $"DIM from C#: %d{md.Z}"

// You can also implement it via an object expression
let md' = { new MyDim }
printfn $"DIM from C# but via Object Expression: %d{md'.Z}"
```

<span data-ttu-id="c6901-143">Puede invalidar una implementación predeterminada con `override` , como invalidar cualquier miembro virtual.</span><span class="sxs-lookup"><span data-stu-id="c6901-143">You can override a default implementation with `override`, like overriding any virtual member.</span></span>

<span data-ttu-id="c6901-144">Cualquier miembro de una interfaz que no tenga una implementación predeterminada todavía debe implementarse explícitamente.</span><span class="sxs-lookup"><span data-stu-id="c6901-144">Any members in an interface that do not have a default implementation must still be explicitly implemented.</span></span>

## <a name="implementing-the-same-interface-at-different-generic-instantiations"></a><span data-ttu-id="c6901-145">Implementar la misma interfaz en distintas instancias genéricas</span><span class="sxs-lookup"><span data-stu-id="c6901-145">Implementing the same interface at different generic instantiations</span></span>

<span data-ttu-id="c6901-146">F # admite la implementación de la misma interfaz en distintas instancias genéricas, como por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c6901-146">F# supports implementing the same interface at different generic instantiations like so:</span></span>

```fsharp
type IA<'T> =
    abstract member Get : unit -> 'T

type MyClass() =
    interface IA<int> with
        member x.Get() = 1
    interface IA<string> with
        member x.Get() = "hello"

let mc = MyClass()
let iaInt = mc :> IA<int>
let iaString = mc :> IA<string>

iaInt.Get() // 1
iaString.Get() // "hello"
```

## <a name="see-also"></a><span data-ttu-id="c6901-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6901-147">See also</span></span>

- [<span data-ttu-id="c6901-148">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="c6901-148">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="c6901-149">Expresiones de objeto</span><span class="sxs-lookup"><span data-stu-id="c6901-149">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="c6901-150">Clases</span><span class="sxs-lookup"><span data-stu-id="c6901-150">Classes</span></span>](classes.md)
