---
title: Extensiones de tipo
description: Obtenga información sobre cómo F# las extensiones de tipo permiten agregar nuevos miembros a un tipo de objeto previamente definido.
ms.date: 02/08/2019
ms.openlocfilehash: 69fb3b771b5334c5771f2ac75341b38c1dad5b90
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982610"
---
# <a name="type-extensions"></a><span data-ttu-id="60d72-103">Extensiones de tipo</span><span class="sxs-lookup"><span data-stu-id="60d72-103">Type extensions</span></span>

<span data-ttu-id="60d72-104">Extensiones de tipo (también denominada _aumentos_) es una familia de características que permiten agregar nuevos miembros a un tipo de objeto previamente definido.</span><span class="sxs-lookup"><span data-stu-id="60d72-104">Type extensions (also called _augmentations_) are a family of features that let you add new members to a previously defined object type.</span></span> <span data-ttu-id="60d72-105">Las tres características son:</span><span class="sxs-lookup"><span data-stu-id="60d72-105">The three features are:</span></span>

* <span data-ttu-id="60d72-106">Extensiones de tipo intrínseco</span><span class="sxs-lookup"><span data-stu-id="60d72-106">Intrinsic type extensions</span></span>
* <span data-ttu-id="60d72-107">Extensiones de tipo opcional</span><span class="sxs-lookup"><span data-stu-id="60d72-107">Optional type extensions</span></span>
* <span data-ttu-id="60d72-108">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="60d72-108">Extension methods</span></span>

<span data-ttu-id="60d72-109">Cada una puede usarse en escenarios diferentes y ofrece un equilibrio entre diferentes.</span><span class="sxs-lookup"><span data-stu-id="60d72-109">Each can be used in different scenarios and has different tradeoffs.</span></span>

## <a name="syntax"></a><span data-ttu-id="60d72-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="60d72-110">Syntax</span></span>

```fsharp
// Intrinsic and optional extensions
type typename with
    member self-identifier.member-name =
        body
    ...

// Extension methods
open System.Runtime.CompilerServices

[<Extension>]
type Extensions() =
    [static] member self-identifier.extension-name (ty: typename, [args]) =
        body
    ...
```

## <a name="intrinsic-type-extensions"></a><span data-ttu-id="60d72-111">Extensiones de tipo intrínseco</span><span class="sxs-lookup"><span data-stu-id="60d72-111">Intrinsic type extensions</span></span>

<span data-ttu-id="60d72-112">Una extensión de tipo intrínseco es un tipo que extiende un tipo definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="60d72-112">An intrinsic type extension is a type extension that extends a user-defined type.</span></span>

<span data-ttu-id="60d72-113">Extensiones de tipo intrínsecas deben definirse en el mismo archivo **y** en el mismo espacio de nombres o módulo como el tipo que están extendiendo.</span><span class="sxs-lookup"><span data-stu-id="60d72-113">Intrinsic type extensions must be defined in the same file **and** in the same namespace or module as the type they're extending.</span></span> <span data-ttu-id="60d72-114">Cualquier otra definición hará que se va a [las extensiones de tipo opcional](type-extensions.md#optional-type-extensions).</span><span class="sxs-lookup"><span data-stu-id="60d72-114">Any other definition will result in them being [optional type extensions](type-extensions.md#optional-type-extensions).</span></span>

<span data-ttu-id="60d72-115">Las extensiones de tipo intrínseco a veces son una forma más limpia para separar la funcionalidad de la declaración de tipos.</span><span class="sxs-lookup"><span data-stu-id="60d72-115">Intrinsic type extensions are sometimes a cleaner way to separate functionality from the type declaration.</span></span> <span data-ttu-id="60d72-116">El ejemplo siguiente muestra cómo definir una extensión de tipo intrínseco:</span><span class="sxs-lookup"><span data-stu-id="60d72-116">The following example shows how to define an intrinsic type extension:</span></span>

```fsharp
namespace Example

type Variant =
    | Num of int
    | Str of string
  
module Variant =
    let print v =
        match v with
        | Num n -> printf "Num %d" n
        | Str s -> printf "Str %s" s

// Add a member to Variant as an extension
type Variant with
    member x.Print() = Variant.print x
```

<span data-ttu-id="60d72-117">Uso de una extensión de tipo le permite separar cada una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="60d72-117">Using a type extension allows you to separate each of the following:</span></span>

* <span data-ttu-id="60d72-118">La declaración de un `Variant` tipo</span><span class="sxs-lookup"><span data-stu-id="60d72-118">The declaration of a `Variant` type</span></span>
* <span data-ttu-id="60d72-119">Funcionalidad para imprimir el `Variant` clase dependiendo de su forma de""</span><span class="sxs-lookup"><span data-stu-id="60d72-119">Functionality to print the `Variant` class depending on its "shape"</span></span>
* <span data-ttu-id="60d72-120">Una manera de obtener acceso a la funcionalidad de impresión con estilo de objeto `.`-notación</span><span class="sxs-lookup"><span data-stu-id="60d72-120">A way to access the printing functionality with object-style `.`-notation</span></span>

<span data-ttu-id="60d72-121">Esta es una alternativa a la definición de todo el contenido como un miembro en `Variant`.</span><span class="sxs-lookup"><span data-stu-id="60d72-121">This is an alternative to defining everything as a member on `Variant`.</span></span> <span data-ttu-id="60d72-122">Aunque no es un enfoque mejor de manera inherente, puede ser una representación más limpia de funcionalidad en algunas situaciones.</span><span class="sxs-lookup"><span data-stu-id="60d72-122">Although it is not an inherently better approach, it can be a cleaner representation of functionality in some situations.</span></span>

<span data-ttu-id="60d72-123">Extensiones de tipo intrínsecas se compilan como miembros del tipo aumentar y que aparecen en el tipo cuando el tipo se examina mediante reflexión.</span><span class="sxs-lookup"><span data-stu-id="60d72-123">Intrinsic type extensions are compiled as members of the type they augment, and appear on the type when the type is examined by reflection.</span></span>

## <a name="optional-type-extensions"></a><span data-ttu-id="60d72-124">Extensiones de tipo opcional</span><span class="sxs-lookup"><span data-stu-id="60d72-124">Optional type extensions</span></span>

<span data-ttu-id="60d72-125">Una extensión de tipo opcional es una extensión que aparece fuera del espacio de nombres, módulo o ensamblado del tipo que se extiende original.</span><span class="sxs-lookup"><span data-stu-id="60d72-125">An optional type extension is an extension that appears outside the original module, namespace, or assembly of the type being extended.</span></span>

<span data-ttu-id="60d72-126">Las extensiones de tipo opcionales son útiles para extender un tipo que no haya definido usted mismo.</span><span class="sxs-lookup"><span data-stu-id="60d72-126">Optional type extensions are useful for extending a type that you have not defined yourself.</span></span> <span data-ttu-id="60d72-127">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="60d72-127">For example:</span></span>

```fsharp
module Extensions

open System.Collections.Generic

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq {
            for x in xs do
                for i in 1 .. n do
                    yield x
        }
```

<span data-ttu-id="60d72-128">Ahora puede acceder a `RepeatElements` como si fuera un miembro de <xref:System.Collections.Generic.IEnumerable%601> siempre y cuando el `Extensions` módulo se abre en el ámbito que está trabajando en.</span><span class="sxs-lookup"><span data-stu-id="60d72-128">You can now access `RepeatElements` as if it's a member of <xref:System.Collections.Generic.IEnumerable%601> as long as the `Extensions` module is opened in the scope that you are working in.</span></span>

<span data-ttu-id="60d72-129">Las extensiones opcionales no aparecen en el tipo extendido cuando se examina mediante reflexión.</span><span class="sxs-lookup"><span data-stu-id="60d72-129">Optional extensions do not appear on the extended type when examined by reflection.</span></span> <span data-ttu-id="60d72-130">Las extensiones opcionales deben estar en módulos y están solo en el ámbito cuando el módulo que contiene la extensión está abierto o si no está en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="60d72-130">Optional extensions must be in modules, and they're only in scope when the module that contains the extension is open or is otherwise in scope.</span></span>

<span data-ttu-id="60d72-131">Miembros de extensión opcionales se compilan en miembros estáticos para el que la instancia del objeto se pasa implícitamente como primer parámetro.</span><span class="sxs-lookup"><span data-stu-id="60d72-131">Optional extension members are compiled to static members for which the object instance is passed implicitly as the first parameter.</span></span> <span data-ttu-id="60d72-132">Sin embargo, actúan como si fueran miembros de instancia o miembros estáticos según cómo se declaran.</span><span class="sxs-lookup"><span data-stu-id="60d72-132">However, they act as if they're instance members or static members according to how they're declared.</span></span>

<span data-ttu-id="60d72-133">No también son visibles para los miembros de extensión opcional C# o los consumidores VB.</span><span class="sxs-lookup"><span data-stu-id="60d72-133">Optional extension members are also not visible to C# or VB consumers.</span></span> <span data-ttu-id="60d72-134">Solo puede ser utilizados en otro F# código.</span><span class="sxs-lookup"><span data-stu-id="60d72-134">They can only be consumed in other F# code.</span></span>

## <a name="generic-limitation-of-intrinsic-and-optional-type-extensions"></a><span data-ttu-id="60d72-135">Limitación genérico de las extensiones de tipo intrínseco y opcionales</span><span class="sxs-lookup"><span data-stu-id="60d72-135">Generic limitation of intrinsic and optional type extensions</span></span>

<span data-ttu-id="60d72-136">Es posible declarar una extensión de tipo en un tipo genérico que se restringe la variable de tipo.</span><span class="sxs-lookup"><span data-stu-id="60d72-136">It's possible to declare a type extension on a generic type where the type variable is constrained.</span></span> <span data-ttu-id="60d72-137">El requisito es que la restricción de la declaración de la extensión coincide con la restricción del tipo declarado.</span><span class="sxs-lookup"><span data-stu-id="60d72-137">The requirement is that the constraint of the extension declaration matches the constraint of the declared type.</span></span>

<span data-ttu-id="60d72-138">Sin embargo, incluso cuando se cumplen las restricciones entre un tipo declarado y una extensión de tipo, es posible que se puede inferir el cuerpo de un miembro extendido que impone un requisito distinto en el parámetro de tipo que el tipo declarado para una restricción.</span><span class="sxs-lookup"><span data-stu-id="60d72-138">However, even when constraints are matched between a declared type and a type extension, it's possible for a constraint to be inferred by the body of an extended member that imposes a different requirement on the type parameter than the declared type.</span></span> <span data-ttu-id="60d72-139">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="60d72-139">For example:</span></span>

```fsharp
open System.Collections.Generic

// NOT POSSIBLE AND FAILS TO COMPILE!
//
// The member 'Sum' has a different requirement on 'T than the type IEnumerable<'T>
type IEnumerable<'T> with
    member this.Sum() = Seq.sum this
```

<span data-ttu-id="60d72-140">No hay ninguna manera de obtener este código funcione con una extensión de tipo opcional:</span><span class="sxs-lookup"><span data-stu-id="60d72-140">There is no way to get this code to work with an optional type extension:</span></span>

* <span data-ttu-id="60d72-141">Tal como está, el `Sum` miembro tiene una restricción diferentes en `'T` (`static member get_Zero` y `static member (+)`) que lo que define la extensión del tipo.</span><span class="sxs-lookup"><span data-stu-id="60d72-141">As is, the `Sum` member has a different constraint on `'T` (`static member get_Zero` and `static member (+)`) than what the type extension defines.</span></span>
* <span data-ttu-id="60d72-142">Modificación de la extensión de tipo para que tenga la misma restricción como `Sum` dejarán de coincidir con la restricción definida en `IEnumerable<'T>`.</span><span class="sxs-lookup"><span data-stu-id="60d72-142">Modifying the type extension to have the same constraint as `Sum` will no longer match the defined constraint on `IEnumerable<'T>`.</span></span>
* <span data-ttu-id="60d72-143">Cambiar `member this.Sum` a `member inline this.Sum` generará un error que no coinciden las restricciones de tipo.</span><span class="sxs-lookup"><span data-stu-id="60d72-143">Changing `member this.Sum` to `member inline this.Sum` will give an error that type constraints are mismatched.</span></span>

<span data-ttu-id="60d72-144">¿Qué es el deseado son métodos estáticos que "flotar en el espacio" y se pueden presentar como si va a extender un tipo.</span><span class="sxs-lookup"><span data-stu-id="60d72-144">What is desired are static methods that "float in space" and can be presented as if they're extending a type.</span></span> <span data-ttu-id="60d72-145">Esto es donde los métodos de extensión que sea necesarios.</span><span class="sxs-lookup"><span data-stu-id="60d72-145">This is where extension methods become necessary.</span></span>

## <a name="extension-methods"></a><span data-ttu-id="60d72-146">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="60d72-146">Extension methods</span></span>

<span data-ttu-id="60d72-147">Por último, los métodos de extensión (a veces denominado "C# miembros de extensión de estilo") se pueden declarar en F# como un método de miembro estático en una clase.</span><span class="sxs-lookup"><span data-stu-id="60d72-147">Finally, extension methods (sometimes called "C# style extension members") can be declared in F# as a static member method on a class.</span></span>

<span data-ttu-id="60d72-148">Métodos de extensión son útiles para cuando desee definir extensiones en un tipo genérico que restringirá la variable de tipo.</span><span class="sxs-lookup"><span data-stu-id="60d72-148">Extension methods are useful for when you wish to define extensions on a generic type that will constrain the type variable.</span></span> <span data-ttu-id="60d72-149">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="60d72-149">For example:</span></span>

```fsharp
namespace Extensions

open System.Runtime.CompilerServices

[<Extension>]
type IEnumerableExtensions() =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

<span data-ttu-id="60d72-150">Cuando se utiliza, este código lo que aparezca como si `Sum` se define en <xref:System.Collections.Generic.IEnumerable%601>, siempre y cuando `Extensions` se ha abierto o está en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="60d72-150">When used, this code will make it appear as if `Sum` is defined on <xref:System.Collections.Generic.IEnumerable%601>, so long as `Extensions` has been opened or is in scope.</span></span>

## <a name="other-remarks"></a><span data-ttu-id="60d72-151">Otros comentarios</span><span class="sxs-lookup"><span data-stu-id="60d72-151">Other remarks</span></span>

<span data-ttu-id="60d72-152">Las extensiones de tipo también tienen los siguientes atributos:</span><span class="sxs-lookup"><span data-stu-id="60d72-152">Type extensions also have the following attributes:</span></span>

* <span data-ttu-id="60d72-153">Se puede extender cualquier tipo que se puede tener acceso.</span><span class="sxs-lookup"><span data-stu-id="60d72-153">Any type that can be accessed can be extended.</span></span>
* <span data-ttu-id="60d72-154">Pueden definir extensiones de tipo intrínsecas y opcional _cualquier_ tipo de miembro, no solo métodos.</span><span class="sxs-lookup"><span data-stu-id="60d72-154">Intrinsic and optional type extensions can define _any_ member type, not just methods.</span></span> <span data-ttu-id="60d72-155">Por lo que las propiedades de extensión también son posibles, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="60d72-155">So extension properties are also possible, for example.</span></span>
* <span data-ttu-id="60d72-156">El `self-identifier` token en el [sintaxis](type-extensions.md#syntax) representa la instancia del tipo que se invoca, igual que los miembros normales.</span><span class="sxs-lookup"><span data-stu-id="60d72-156">The `self-identifier` token in the [syntax](type-extensions.md#syntax) represents the instance of the type being invoked, just like ordinary members.</span></span>
* <span data-ttu-id="60d72-157">Miembros extendidos pueden ser estáticos o miembros de instancia.</span><span class="sxs-lookup"><span data-stu-id="60d72-157">Extended members can be static or instance members.</span></span>
* <span data-ttu-id="60d72-158">Las variables de tipo en una extensión de tipo deben coincidir con las restricciones del tipo declarado.</span><span class="sxs-lookup"><span data-stu-id="60d72-158">Type variables on a type extension must match the constraints of the declared type.</span></span>

<span data-ttu-id="60d72-159">También existen las siguientes limitaciones para las extensiones de tipo:</span><span class="sxs-lookup"><span data-stu-id="60d72-159">The following limitations also exist for type extensions:</span></span>

* <span data-ttu-id="60d72-160">Las extensiones de tipo no admiten métodos virtuales o abstractos.</span><span class="sxs-lookup"><span data-stu-id="60d72-160">Type extensions do not support virtual or abstract methods.</span></span>
* <span data-ttu-id="60d72-161">Las extensiones de tipo no admiten los métodos de invalidación como aumentos.</span><span class="sxs-lookup"><span data-stu-id="60d72-161">Type extensions do not support override methods as augmentations.</span></span>
* <span data-ttu-id="60d72-162">No se admiten las extensiones de tipo [parámetros tipo resueltos estáticamente](generics/statically-resolved-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="60d72-162">Type extensions do not support [Statically Resolved Type Parameters](generics/statically-resolved-type-parameters.md).</span></span>
* <span data-ttu-id="60d72-163">Extensiones de tipo opcionales no admiten constructores como aumentos.</span><span class="sxs-lookup"><span data-stu-id="60d72-163">Optional Type extensions do not support constructors as augmentations.</span></span>
* <span data-ttu-id="60d72-164">Las extensiones de tipo no se pueden definir en [abreviaturas de tipo](type-abbreviations.md).</span><span class="sxs-lookup"><span data-stu-id="60d72-164">Type extensions cannot be defined on [type abbreviations](type-abbreviations.md).</span></span>
* <span data-ttu-id="60d72-165">Las extensiones de tipo no son válidas para `byref<'T>` (aunque se puede declarar).</span><span class="sxs-lookup"><span data-stu-id="60d72-165">Type extensions are not valid for `byref<'T>` (though they can be declared).</span></span>
* <span data-ttu-id="60d72-166">Las extensiones de tipo no son válidas para los atributos (aunque se puede declarar).</span><span class="sxs-lookup"><span data-stu-id="60d72-166">Type extensions are not valid for attributes (though they can be declared).</span></span>
* <span data-ttu-id="60d72-167">Puede definir extensiones que sobrecargan otros métodos del mismo nombre, pero el F# compilador da preferencia a los métodos que no sean de extensión si hay una llamada ambigua.</span><span class="sxs-lookup"><span data-stu-id="60d72-167">You can define extensions that overload other methods of the same name, but the F# compiler gives preference to non-extension methods if there is an ambiguous call.</span></span>

<span data-ttu-id="60d72-168">Por último, si existen varias extensiones de tipo intrínsecas para un tipo, todos los miembros deben ser únicos.</span><span class="sxs-lookup"><span data-stu-id="60d72-168">Finally, if multiple intrinsic type extensions exist for one type, all members must be unique.</span></span> <span data-ttu-id="60d72-169">Para las extensiones de tipo opcional, los miembros de las extensiones de tipo diferente en el mismo tipo pueden tener los mismos nombres.</span><span class="sxs-lookup"><span data-stu-id="60d72-169">For optional type extensions, members in different type extensions to the same type can have the same names.</span></span> <span data-ttu-id="60d72-170">Se producen errores de ambigüedad sólo si el código de cliente abre dos ámbitos diferentes que definen los mismos nombres de miembro.</span><span class="sxs-lookup"><span data-stu-id="60d72-170">Ambiguity errors occur only if client code opens two different scopes that define the same member names.</span></span>

## <a name="see-also"></a><span data-ttu-id="60d72-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="60d72-171">See also</span></span>

- [<span data-ttu-id="60d72-172">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="60d72-172">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="60d72-173">Miembros</span><span class="sxs-lookup"><span data-stu-id="60d72-173">Members</span></span>](members/index.md)
