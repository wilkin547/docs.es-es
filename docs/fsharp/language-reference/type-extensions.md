---
title: Extensiones de tipo
description: Obtenga información F# sobre cómo las extensiones de tipo permiten agregar nuevos miembros a un tipo de objeto definido previamente.
ms.date: 02/05/2020
ms.openlocfilehash: 9ab3a007783f67fd8d80cff840ac3085fdcd60f7
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77092686"
---
# <a name="type-extensions"></a><span data-ttu-id="aca28-103">Extensiones de tipo</span><span class="sxs-lookup"><span data-stu-id="aca28-103">Type extensions</span></span>

<span data-ttu-id="aca28-104">Las extensiones de tipo (también denominadas _aumentos_) son una familia de características que permiten agregar nuevos miembros a un tipo de objeto definido previamente.</span><span class="sxs-lookup"><span data-stu-id="aca28-104">Type extensions (also called _augmentations_) are a family of features that let you add new members to a previously defined object type.</span></span> <span data-ttu-id="aca28-105">Las tres características son:</span><span class="sxs-lookup"><span data-stu-id="aca28-105">The three features are:</span></span>

- <span data-ttu-id="aca28-106">Extensiones de tipo intrínsecas</span><span class="sxs-lookup"><span data-stu-id="aca28-106">Intrinsic type extensions</span></span>
- <span data-ttu-id="aca28-107">Extensiones de tipo opcionales</span><span class="sxs-lookup"><span data-stu-id="aca28-107">Optional type extensions</span></span>
- <span data-ttu-id="aca28-108">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="aca28-108">Extension methods</span></span>

<span data-ttu-id="aca28-109">Cada se puede usar en escenarios diferentes y tiene diferentes inconvenientes.</span><span class="sxs-lookup"><span data-stu-id="aca28-109">Each can be used in different scenarios and has different tradeoffs.</span></span>

## <a name="syntax"></a><span data-ttu-id="aca28-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aca28-110">Syntax</span></span>

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
    [<Extension>]
    static member self-identifier.extension-name (ty: typename, [args]) =
        body
    ...
```

## <a name="intrinsic-type-extensions"></a><span data-ttu-id="aca28-111">Extensiones de tipo intrínsecas</span><span class="sxs-lookup"><span data-stu-id="aca28-111">Intrinsic type extensions</span></span>

<span data-ttu-id="aca28-112">Una extensión de tipo intrínseco es una extensión de tipo que extiende un tipo definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="aca28-112">An intrinsic type extension is a type extension that extends a user-defined type.</span></span>

<span data-ttu-id="aca28-113">Las extensiones de tipo intrínseco se deben definir en el mismo archivo **y** en el mismo espacio de nombres o módulo que el tipo que están extendiendo.</span><span class="sxs-lookup"><span data-stu-id="aca28-113">Intrinsic type extensions must be defined in the same file **and** in the same namespace or module as the type they're extending.</span></span> <span data-ttu-id="aca28-114">Cualquier otra definición dará como resultado extensiones de [tipo opcionales](type-extensions.md#optional-type-extensions).</span><span class="sxs-lookup"><span data-stu-id="aca28-114">Any other definition will result in them being [optional type extensions](type-extensions.md#optional-type-extensions).</span></span>

<span data-ttu-id="aca28-115">Las extensiones de tipo intrínseco a veces son una forma más limpia de separar la funcionalidad de la declaración de tipos.</span><span class="sxs-lookup"><span data-stu-id="aca28-115">Intrinsic type extensions are sometimes a cleaner way to separate functionality from the type declaration.</span></span> <span data-ttu-id="aca28-116">En el ejemplo siguiente se muestra cómo definir una extensión de tipo intrínseco:</span><span class="sxs-lookup"><span data-stu-id="aca28-116">The following example shows how to define an intrinsic type extension:</span></span>

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

<span data-ttu-id="aca28-117">El uso de una extensión de tipo le permite separar cada uno de los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="aca28-117">Using a type extension allows you to separate each of the following:</span></span>

- <span data-ttu-id="aca28-118">Declaración de un tipo de `Variant`</span><span class="sxs-lookup"><span data-stu-id="aca28-118">The declaration of a `Variant` type</span></span>
- <span data-ttu-id="aca28-119">Funcionalidad para imprimir la clase `Variant` en función de su "forma"</span><span class="sxs-lookup"><span data-stu-id="aca28-119">Functionality to print the `Variant` class depending on its "shape"</span></span>
- <span data-ttu-id="aca28-120">Una manera de tener acceso a la funcionalidad de impresión con la notación de `.`de estilo de objeto</span><span class="sxs-lookup"><span data-stu-id="aca28-120">A way to access the printing functionality with object-style `.`-notation</span></span>

<span data-ttu-id="aca28-121">Esta es una alternativa a la definición de todo como miembro en `Variant`.</span><span class="sxs-lookup"><span data-stu-id="aca28-121">This is an alternative to defining everything as a member on `Variant`.</span></span> <span data-ttu-id="aca28-122">Aunque no es un enfoque bastante mejor, puede ser una representación más limpia de la funcionalidad en algunas situaciones.</span><span class="sxs-lookup"><span data-stu-id="aca28-122">Although it is not an inherently better approach, it can be a cleaner representation of functionality in some situations.</span></span>

<span data-ttu-id="aca28-123">Las extensiones de tipo intrínseco se compilan como miembros del tipo que aumentan y aparecen en el tipo cuando la reflexión examina el tipo.</span><span class="sxs-lookup"><span data-stu-id="aca28-123">Intrinsic type extensions are compiled as members of the type they augment, and appear on the type when the type is examined by reflection.</span></span>

## <a name="optional-type-extensions"></a><span data-ttu-id="aca28-124">Extensiones de tipo opcionales</span><span class="sxs-lookup"><span data-stu-id="aca28-124">Optional type extensions</span></span>

<span data-ttu-id="aca28-125">Una extensión de tipo opcional es una extensión que aparece fuera del módulo, espacio de nombres o ensamblado original del tipo que se va a extender.</span><span class="sxs-lookup"><span data-stu-id="aca28-125">An optional type extension is an extension that appears outside the original module, namespace, or assembly of the type being extended.</span></span>

<span data-ttu-id="aca28-126">Las extensiones de tipo opcionales son útiles para extender un tipo que no se ha definido.</span><span class="sxs-lookup"><span data-stu-id="aca28-126">Optional type extensions are useful for extending a type that you have not defined yourself.</span></span> <span data-ttu-id="aca28-127">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="aca28-127">For example:</span></span>

```fsharp
module Extensions

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq {
            for x in xs do
                for _ in 1 .. n -> x
        }
```

<span data-ttu-id="aca28-128">Ahora puede tener acceso a `RepeatElements` como si es miembro de <xref:System.Collections.Generic.IEnumerable%601> siempre que el módulo de `Extensions` se abra en el ámbito en el que está trabajando.</span><span class="sxs-lookup"><span data-stu-id="aca28-128">You can now access `RepeatElements` as if it's a member of <xref:System.Collections.Generic.IEnumerable%601> as long as the `Extensions` module is opened in the scope that you are working in.</span></span>

<span data-ttu-id="aca28-129">Las extensiones opcionales no aparecen en el tipo extendido cuando se examinan por reflexión.</span><span class="sxs-lookup"><span data-stu-id="aca28-129">Optional extensions do not appear on the extended type when examined by reflection.</span></span> <span data-ttu-id="aca28-130">Las extensiones opcionales deben estar en módulos y solo están en el ámbito cuando el módulo que contiene la extensión está abierto o está en el ámbito de otra forma.</span><span class="sxs-lookup"><span data-stu-id="aca28-130">Optional extensions must be in modules, and they're only in scope when the module that contains the extension is open or is otherwise in scope.</span></span>

<span data-ttu-id="aca28-131">Los miembros de extensión opcionales se compilan en miembros estáticos para los que la instancia de objeto se pasa implícitamente como el primer parámetro.</span><span class="sxs-lookup"><span data-stu-id="aca28-131">Optional extension members are compiled to static members for which the object instance is passed implicitly as the first parameter.</span></span> <span data-ttu-id="aca28-132">Sin embargo, actúan como si fueran miembros de instancia o miembros estáticos según cómo se declaran.</span><span class="sxs-lookup"><span data-stu-id="aca28-132">However, they act as if they're instance members or static members according to how they're declared.</span></span>

<span data-ttu-id="aca28-133">Los miembros de extensión opcionales tampoco son visibles C# para los consumidores o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="aca28-133">Optional extension members are also not visible to C# or Visual Basic consumers.</span></span> <span data-ttu-id="aca28-134">Solo se pueden consumir en otro F# código.</span><span class="sxs-lookup"><span data-stu-id="aca28-134">They can only be consumed in other F# code.</span></span>

## <a name="generic-limitation-of-intrinsic-and-optional-type-extensions"></a><span data-ttu-id="aca28-135">Limitación genérica de las extensiones de tipo intrínsecas y opcionales</span><span class="sxs-lookup"><span data-stu-id="aca28-135">Generic limitation of intrinsic and optional type extensions</span></span>

<span data-ttu-id="aca28-136">Es posible declarar una extensión de tipo en un tipo genérico en el que la variable de tipo está restringida.</span><span class="sxs-lookup"><span data-stu-id="aca28-136">It's possible to declare a type extension on a generic type where the type variable is constrained.</span></span> <span data-ttu-id="aca28-137">El requisito es que la restricción de la declaración de extensión coincide con la restricción del tipo declarado.</span><span class="sxs-lookup"><span data-stu-id="aca28-137">The requirement is that the constraint of the extension declaration matches the constraint of the declared type.</span></span>

<span data-ttu-id="aca28-138">Sin embargo, incluso cuando se hace coincidir las restricciones entre un tipo declarado y una extensión de tipo, es posible que una restricción se infiera por el cuerpo de un miembro extendido que impone un requisito diferente en el parámetro de tipo que el tipo declarado.</span><span class="sxs-lookup"><span data-stu-id="aca28-138">However, even when constraints are matched between a declared type and a type extension, it's possible for a constraint to be inferred by the body of an extended member that imposes a different requirement on the type parameter than the declared type.</span></span> <span data-ttu-id="aca28-139">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="aca28-139">For example:</span></span>

```fsharp
open System.Collections.Generic

// NOT POSSIBLE AND FAILS TO COMPILE!
//
// The member 'Sum' has a different requirement on 'T than the type IEnumerable<'T>
type IEnumerable<'T> with
    member this.Sum() = Seq.sum this
```

<span data-ttu-id="aca28-140">No hay ninguna manera de obtener este código para trabajar con una extensión de tipo opcional:</span><span class="sxs-lookup"><span data-stu-id="aca28-140">There is no way to get this code to work with an optional type extension:</span></span>

- <span data-ttu-id="aca28-141">Tal y como está, el miembro de `Sum` tiene una restricción diferente en `'T` (`static member get_Zero` y `static member (+)`) de la que define la extensión de tipo.</span><span class="sxs-lookup"><span data-stu-id="aca28-141">As is, the `Sum` member has a different constraint on `'T` (`static member get_Zero` and `static member (+)`) than what the type extension defines.</span></span>
- <span data-ttu-id="aca28-142">La modificación de la extensión de tipo para que tenga la misma restricción que `Sum` ya no coincidirá con la restricción definida en `IEnumerable<'T>`.</span><span class="sxs-lookup"><span data-stu-id="aca28-142">Modifying the type extension to have the same constraint as `Sum` will no longer match the defined constraint on `IEnumerable<'T>`.</span></span>
- <span data-ttu-id="aca28-143">Al cambiar `member this.Sum` a `member inline this.Sum`, se producirá un error que indica que las restricciones de tipo no coinciden.</span><span class="sxs-lookup"><span data-stu-id="aca28-143">Changing `member this.Sum` to `member inline this.Sum` will give an error that type constraints are mismatched.</span></span>

<span data-ttu-id="aca28-144">Lo que se desea son los métodos estáticos que "flotan espacio" y se pueden presentar como si estuvieran extendiendo un tipo.</span><span class="sxs-lookup"><span data-stu-id="aca28-144">What is desired are static methods that "float in space" and can be presented as if they're extending a type.</span></span> <span data-ttu-id="aca28-145">Aquí es donde los métodos de extensión son necesarios.</span><span class="sxs-lookup"><span data-stu-id="aca28-145">This is where extension methods become necessary.</span></span>

## <a name="extension-methods"></a><span data-ttu-id="aca28-146">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="aca28-146">Extension methods</span></span>

<span data-ttu-id="aca28-147">Por último, los métodos de extensión (C# a veces denominados "miembros de extensión de F# estilo") se pueden declarar en como un método de miembro estático en una clase.</span><span class="sxs-lookup"><span data-stu-id="aca28-147">Finally, extension methods (sometimes called "C# style extension members") can be declared in F# as a static member method on a class.</span></span>

<span data-ttu-id="aca28-148">Los métodos de extensión son útiles cuando se desea definir extensiones en un tipo genérico que restrinja la variable de tipo.</span><span class="sxs-lookup"><span data-stu-id="aca28-148">Extension methods are useful for when you wish to define extensions on a generic type that will constrain the type variable.</span></span> <span data-ttu-id="aca28-149">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="aca28-149">For example:</span></span>

```fsharp
namespace Extensions

open System.Runtime.CompilerServices

[<Extension>]
type IEnumerableExtensions =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

<span data-ttu-id="aca28-150">Cuando se usa, este código aparecerá como si `Sum` se define en <xref:System.Collections.Generic.IEnumerable%601>, siempre y cuando `Extensions` se haya abierto o esté en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="aca28-150">When used, this code will make it appear as if `Sum` is defined on <xref:System.Collections.Generic.IEnumerable%601>, so long as `Extensions` has been opened or is in scope.</span></span>

<span data-ttu-id="aca28-151">Para que la extensión esté disponible para el código VB.NET, se requiere un `ExtensionAttribute` adicional en el nivel de ensamblado:</span><span class="sxs-lookup"><span data-stu-id="aca28-151">For the extension to be available to VB.NET code, an extra `ExtensionAttribute` is required at the assembly level:</span></span>

```fsharp
module AssemblyInfo
open System.Runtime.CompilerServices
[<assembly:Extension>]
do ()
```

## <a name="other-remarks"></a><span data-ttu-id="aca28-152">Otros comentarios</span><span class="sxs-lookup"><span data-stu-id="aca28-152">Other remarks</span></span>

<span data-ttu-id="aca28-153">Las extensiones de tipo también tienen los siguientes atributos:</span><span class="sxs-lookup"><span data-stu-id="aca28-153">Type extensions also have the following attributes:</span></span>

- <span data-ttu-id="aca28-154">Se puede extender cualquier tipo al que se pueda tener acceso.</span><span class="sxs-lookup"><span data-stu-id="aca28-154">Any type that can be accessed can be extended.</span></span>
- <span data-ttu-id="aca28-155">Las extensiones de tipo intrínseca y opcional pueden definir _cualquier_ tipo de miembro, no solo los métodos.</span><span class="sxs-lookup"><span data-stu-id="aca28-155">Intrinsic and optional type extensions can define _any_ member type, not just methods.</span></span> <span data-ttu-id="aca28-156">Por ejemplo, las propiedades de extensión también son posibles.</span><span class="sxs-lookup"><span data-stu-id="aca28-156">So extension properties are also possible, for example.</span></span>
- <span data-ttu-id="aca28-157">El token de `self-identifier` en la [Sintaxis](type-extensions.md#syntax) representa la instancia del tipo que se invoca, al igual que los miembros ordinarios.</span><span class="sxs-lookup"><span data-stu-id="aca28-157">The `self-identifier` token in the [syntax](type-extensions.md#syntax) represents the instance of the type being invoked, just like ordinary members.</span></span>
- <span data-ttu-id="aca28-158">Los miembros extendidos pueden ser miembros estáticos o de instancia.</span><span class="sxs-lookup"><span data-stu-id="aca28-158">Extended members can be static or instance members.</span></span>
- <span data-ttu-id="aca28-159">Las variables de tipo en una extensión de tipo deben coincidir con las restricciones del tipo declarado.</span><span class="sxs-lookup"><span data-stu-id="aca28-159">Type variables on a type extension must match the constraints of the declared type.</span></span>

<span data-ttu-id="aca28-160">También existen las siguientes limitaciones para las extensiones de tipo:</span><span class="sxs-lookup"><span data-stu-id="aca28-160">The following limitations also exist for type extensions:</span></span>

- <span data-ttu-id="aca28-161">Las extensiones de tipo no admiten métodos virtuales o abstractos.</span><span class="sxs-lookup"><span data-stu-id="aca28-161">Type extensions do not support virtual or abstract methods.</span></span>
- <span data-ttu-id="aca28-162">Las extensiones de tipo no admiten métodos de invalidación como aumentos.</span><span class="sxs-lookup"><span data-stu-id="aca28-162">Type extensions do not support override methods as augmentations.</span></span>
- <span data-ttu-id="aca28-163">Las extensiones de tipo no admiten [parámetros de tipo resueltos estáticamente](./generics/statically-resolved-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="aca28-163">Type extensions do not support [Statically Resolved Type Parameters](./generics/statically-resolved-type-parameters.md).</span></span>
- <span data-ttu-id="aca28-164">Las extensiones de tipo opcionales no admiten constructores como aumentos.</span><span class="sxs-lookup"><span data-stu-id="aca28-164">Optional Type extensions do not support constructors as augmentations.</span></span>
- <span data-ttu-id="aca28-165">Las extensiones de tipo no se pueden definir en las [abreviaturas de tipo](type-abbreviations.md).</span><span class="sxs-lookup"><span data-stu-id="aca28-165">Type extensions cannot be defined on [type abbreviations](type-abbreviations.md).</span></span>
- <span data-ttu-id="aca28-166">Las extensiones de tipo no son válidas para `byref<'T>` (aunque se pueden declarar).</span><span class="sxs-lookup"><span data-stu-id="aca28-166">Type extensions are not valid for `byref<'T>` (though they can be declared).</span></span>
- <span data-ttu-id="aca28-167">Las extensiones de tipo no son válidas para los atributos (aunque se pueden declarar).</span><span class="sxs-lookup"><span data-stu-id="aca28-167">Type extensions are not valid for attributes (though they can be declared).</span></span>
- <span data-ttu-id="aca28-168">Puede definir extensiones que sobrecarguen otros métodos del mismo nombre, pero el F# compilador da preferencia a los métodos que no son de extensión si hay una llamada ambigua.</span><span class="sxs-lookup"><span data-stu-id="aca28-168">You can define extensions that overload other methods of the same name, but the F# compiler gives preference to non-extension methods if there is an ambiguous call.</span></span>

<span data-ttu-id="aca28-169">Por último, si existen varias extensiones de tipo intrínsecas para un tipo, todos los miembros deben ser únicos.</span><span class="sxs-lookup"><span data-stu-id="aca28-169">Finally, if multiple intrinsic type extensions exist for one type, all members must be unique.</span></span> <span data-ttu-id="aca28-170">En el caso de las extensiones de tipo opcionales, los miembros de diferentes extensiones de tipo al mismo tipo pueden tener los mismos nombres.</span><span class="sxs-lookup"><span data-stu-id="aca28-170">For optional type extensions, members in different type extensions to the same type can have the same names.</span></span> <span data-ttu-id="aca28-171">Los errores de ambigüedad solo se producen si el código de cliente abre dos ámbitos diferentes que definen los mismos nombres de miembro.</span><span class="sxs-lookup"><span data-stu-id="aca28-171">Ambiguity errors occur only if client code opens two different scopes that define the same member names.</span></span>

## <a name="see-also"></a><span data-ttu-id="aca28-172">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aca28-172">See also</span></span>

- [<span data-ttu-id="aca28-173">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="aca28-173">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="aca28-174">Miembros</span><span class="sxs-lookup"><span data-stu-id="aca28-174">Members</span></span>](./members/index.md)
