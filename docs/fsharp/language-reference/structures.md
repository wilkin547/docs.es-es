---
title: Estructuras (F#)
description: 'Obtenga información sobre la estructura de F #, un tipo de objeto compacto a menudo más eficaz que una clase para los tipos con una pequeña cantidad de datos y un comportamiento simple.'
ms.date: 05/16/2016
ms.openlocfilehash: 08af88132dda28883e246b94585ff4ed8bd2f16a
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "48845308"
---
# <a name="structures"></a><span data-ttu-id="d2e90-103">Estructuras</span><span class="sxs-lookup"><span data-stu-id="d2e90-103">Structures</span></span>

<span data-ttu-id="d2e90-104">Un *estructura* es un tipo de objeto compacto que puede ser más eficaz que una clase para tipos que tienen una pequeña cantidad de datos y un comportamiento simple.</span><span class="sxs-lookup"><span data-stu-id="d2e90-104">A *structure* is a compact object type that can be more efficient than a class for types that have a small amount of data and simple behavior.</span></span>

## <a name="syntax"></a><span data-ttu-id="d2e90-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2e90-105">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    struct
        type-definition-elements-and-members
    end
// or
[ attributes ]
[<StructAttribute>]
type [accessibility-modifier] type-name =
    type-definition-elements-and-members
```

## <a name="remarks"></a><span data-ttu-id="d2e90-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d2e90-106">Remarks</span></span>

<span data-ttu-id="d2e90-107">Las estructuras son *los tipos de valor*, lo que significa que se almacenan directamente en la pila o, cuando se usan como campos o los elementos de matriz, alineados en el elemento primario del tipo.</span><span class="sxs-lookup"><span data-stu-id="d2e90-107">Structures are *value types*, which means that they are stored directly on the stack or, when they are used as fields or array elements, inline in the parent type.</span></span> <span data-ttu-id="d2e90-108">A diferencia de los registros y las clases, las estructuras tienen semántica de paso por valor.</span><span class="sxs-lookup"><span data-stu-id="d2e90-108">Unlike classes and records, structures have pass-by-value semantics.</span></span> <span data-ttu-id="d2e90-109">Esto significa que son útiles principalmente para pequeños agregados de datos a los que accede y que se copian con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="d2e90-109">This means that they are useful primarily for small aggregates of data that are accessed and copied frequently.</span></span>

<span data-ttu-id="d2e90-110">En la sintaxis anterior, se muestran dos formularios.</span><span class="sxs-lookup"><span data-stu-id="d2e90-110">In the previous syntax, two forms are shown.</span></span> <span data-ttu-id="d2e90-111">La primera no es la sintaxis ligera; sin embargo, se utiliza frecuentemente porque, cuando se usan las palabras clave `struct` y `end`, se puede omitir el atributo `StructAttribute`, que aparece en el segundo formulario.</span><span class="sxs-lookup"><span data-stu-id="d2e90-111">The first is not the lightweight syntax, but it is nevertheless frequently used because, when you use the `struct` and `end` keywords, you can omit the `StructAttribute` attribute, which appears in the second form.</span></span> <span data-ttu-id="d2e90-112">`StructAttribute` se puede abreviar como `Struct`.</span><span class="sxs-lookup"><span data-stu-id="d2e90-112">You can abbreviate `StructAttribute` to just `Struct`.</span></span>

<span data-ttu-id="d2e90-113">El *-definition-elementos-y-miembros de tipo* en la sintaxis anterior representa definiciones y declaraciones de miembros.</span><span class="sxs-lookup"><span data-stu-id="d2e90-113">The *type-definition-elements-and-members* in the previous syntax represents member declarations and definitions.</span></span> <span data-ttu-id="d2e90-114">Las estructuras pueden tener constructores y campos mutables e inmutables, y pueden declarar implementaciones de interfaces y miembros.</span><span class="sxs-lookup"><span data-stu-id="d2e90-114">Structures can have constructors and mutable and immutable fields, and they can declare members and interface implementations.</span></span> <span data-ttu-id="d2e90-115">Para obtener más información, consulte [miembros](members/index.md).</span><span class="sxs-lookup"><span data-stu-id="d2e90-115">For more information, see [Members](members/index.md).</span></span>

<span data-ttu-id="d2e90-116">Las estructuras no pueden participar en la herencia, no pueden contener enlaces `let` ni `do`, y no puede contener de forma recursiva campos de su propio tipo (aunque pueden contener celdas de referencia que hagan referencia a su propio tipo).</span><span class="sxs-lookup"><span data-stu-id="d2e90-116">Structures cannot participate in inheritance, cannot contain `let` or `do` bindings, and cannot recursively contain fields of their own type (although they can contain reference cells that reference their own type).</span></span>

<span data-ttu-id="d2e90-117">Dado que las estructuras no permiten enlaces `let`, debe declarar campos en estructuras mediante el uso de la palabra clave `val`.</span><span class="sxs-lookup"><span data-stu-id="d2e90-117">Because structures do not allow `let` bindings, you must declare fields in structures by using the `val` keyword.</span></span> <span data-ttu-id="d2e90-118">La palabra clave `val` define un campo y su tipo, pero no permite la inicialización.</span><span class="sxs-lookup"><span data-stu-id="d2e90-118">The `val` keyword defines a field and its type but does not allow initialization.</span></span> <span data-ttu-id="d2e90-119">En su lugar, las declaraciones `val` se inicializan en cero o null.</span><span class="sxs-lookup"><span data-stu-id="d2e90-119">Instead, `val` declarations are initialized to zero or null.</span></span> <span data-ttu-id="d2e90-120">Por este motivo, las estructuras que tienen un constructor implícito (es decir, los parámetros que se proporcionan inmediatamente después del nombre de la estructura en la declaración) requieren que las declaraciones `val` se anoten con el atributo `DefaultValue`.</span><span class="sxs-lookup"><span data-stu-id="d2e90-120">For this reason, structures that have an implicit constructor (that is, parameters that are given immediately after the structure name in the declaration) require that `val` declarations be annotated with the `DefaultValue` attribute.</span></span> <span data-ttu-id="d2e90-121">Las estructuras que tienen un constructor definido todavía admiten la inicialización en cero.</span><span class="sxs-lookup"><span data-stu-id="d2e90-121">Structures that have a defined constructor still support zero-initialization.</span></span> <span data-ttu-id="d2e90-122">Por lo tanto, el atributo `DefaultValue` es una declaración de que ese valor cero es válido para el campo.</span><span class="sxs-lookup"><span data-stu-id="d2e90-122">Therefore, the `DefaultValue` attribute is a declaration that such a zero value is valid for the field.</span></span> <span data-ttu-id="d2e90-123">Los constructores implícitos de las estructuras no realizan ninguna acción porque los enlaces `let` y `do` no están permitidos en el tipo, pero los valores de parámetro de constructor implícito pasados están disponibles como campos privados.</span><span class="sxs-lookup"><span data-stu-id="d2e90-123">Implicit constructors for structures do not perform any actions because `let` and `do` bindings aren’t allowed on the type, but the implicit constructor parameter values passed in are available as private fields.</span></span>

<span data-ttu-id="d2e90-124">Los constructores explícitos podrían implicar la inicialización de los valores de campo.</span><span class="sxs-lookup"><span data-stu-id="d2e90-124">Explicit constructors might involve initialization of field values.</span></span> <span data-ttu-id="d2e90-125">Cuando se tiene una estructura con un constructor explícito, se admite la inicialización en cero; sin embargo, no se utiliza el atributo `DefaultValue` en las declaraciones `val` porque entra en conflicto con el constructor explícito.</span><span class="sxs-lookup"><span data-stu-id="d2e90-125">When you have a structure that has an explicit constructor, it still supports zero-initialization; however, you do not use the `DefaultValue` attribute on the `val` declarations because it conflicts with the explicit constructor.</span></span> <span data-ttu-id="d2e90-126">Para obtener más información acerca de `val` declaraciones, vea [campos explícitos: el `val` palabra clave](members/explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="d2e90-126">For more information about `val` declarations, see [Explicit Fields: The `val` Keyword](members/explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="d2e90-127">Los atributos y modificadores de accesibilidad están permitidos en las estructuras y siguen las mismas reglas que las de otros tipos.</span><span class="sxs-lookup"><span data-stu-id="d2e90-127">Attributes and accessibility modifiers are allowed on structures, and follow the same rules as those for other types.</span></span> <span data-ttu-id="d2e90-128">Para obtener más información, consulte [atributos](attributes.md) y [Control de acceso](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="d2e90-128">For more information, see [Attributes](attributes.md) and [Access Control](access-control.md).</span></span>

<span data-ttu-id="d2e90-129">Los siguientes ejemplos de código ilustran las definiciones de la estructura.</span><span class="sxs-lookup"><span data-stu-id="d2e90-129">The following code examples illustrate structure definitions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="byreflike-structs"></a><span data-ttu-id="d2e90-130">Structs ByRefLike</span><span class="sxs-lookup"><span data-stu-id="d2e90-130">ByRefLike structs</span></span>

<span data-ttu-id="d2e90-131">Puede definir sus propias estructuras que pueden cumplir `byref`-como semántica: vea [Zkratka](byrefs.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d2e90-131">You can define your own structs that can adhere to `byref`-like semantics: see [Byrefs](byrefs.md) for more information.</span></span> <span data-ttu-id="d2e90-132">Esto se realiza con el <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> atributo:</span><span class="sxs-lookup"><span data-stu-id="d2e90-132">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="d2e90-133">`IsByRefLike` no implica `Struct`.</span><span class="sxs-lookup"><span data-stu-id="d2e90-133">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="d2e90-134">Deben estar presentes en el tipo.</span><span class="sxs-lookup"><span data-stu-id="d2e90-134">Both must be present on the type.</span></span>

<span data-ttu-id="d2e90-135">Un "`byref`-como" struct en F # es un tipo de valor de límite de la pila.</span><span class="sxs-lookup"><span data-stu-id="d2e90-135">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="d2e90-136">Nunca se asigna en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="d2e90-136">It is never allocated on the managed heap.</span></span> <span data-ttu-id="d2e90-137">Un `byref`-como struct es útil para la programación de alto rendimiento, ya que se aplica con el conjunto de controles sólidos sobre la duración y no captura.</span><span class="sxs-lookup"><span data-stu-id="d2e90-137">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="d2e90-138">Las reglas son:</span><span class="sxs-lookup"><span data-stu-id="d2e90-138">The rules are:</span></span>

* <span data-ttu-id="d2e90-139">Se puede usar como parámetros de función, parámetros de método, las variables locales, devuelve el método.</span><span class="sxs-lookup"><span data-stu-id="d2e90-139">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="d2e90-140">Que no pueden ser estáticos o miembros de una clase o estructura normal de instancia.</span><span class="sxs-lookup"><span data-stu-id="d2e90-140">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="d2e90-141">No se puede capturar cualquier construcción de cierre (`async` métodos o expresiones lambda).</span><span class="sxs-lookup"><span data-stu-id="d2e90-141">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="d2e90-142">No se puede usar como un parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="d2e90-142">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="d2e90-143">Aunque estas reglas encarecidamente restringen el uso, lo hacen para cumplir la promesa de informática de alto rendimiento de una manera segura.</span><span class="sxs-lookup"><span data-stu-id="d2e90-143">Although these rules very strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="readonly-structs"></a><span data-ttu-id="d2e90-144">Estructuras ReadOnly</span><span class="sxs-lookup"><span data-stu-id="d2e90-144">ReadOnly structs</span></span>

<span data-ttu-id="d2e90-145">Puede anotar structs con el <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> atributo.</span><span class="sxs-lookup"><span data-stu-id="d2e90-145">You can annotate structs with the <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> attribute.</span></span> <span data-ttu-id="d2e90-146">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d2e90-146">For example:</span></span>

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="d2e90-147">`IsReadOnly` no implica `Struct`.</span><span class="sxs-lookup"><span data-stu-id="d2e90-147">`IsReadOnly` does not imply `Struct`.</span></span> <span data-ttu-id="d2e90-148">Debe agregar ambos para tener un `IsReadOnly` struct.</span><span class="sxs-lookup"><span data-stu-id="d2e90-148">You must add both to have an `IsReadOnly` struct.</span></span>

<span data-ttu-id="d2e90-149">Uso de este atributo emite metadatos, lo que permite F # y C# saber para tratarlo como `inref<'T>` y `in ref`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="d2e90-149">Use of this attribute emits metadata letting F# and C# know to treat it as `inref<'T>` and `in ref`, respectively.</span></span>

<span data-ttu-id="d2e90-150">Definir un valor mutable dentro de un struct de solo lectura, produce un error.</span><span class="sxs-lookup"><span data-stu-id="d2e90-150">Defining a mutable value inside of a readonly struct produces an error.</span></span>

## <a name="struct-records-and-discriminated-unions"></a><span data-ttu-id="d2e90-151">Struct registros y uniones discriminadas</span><span class="sxs-lookup"><span data-stu-id="d2e90-151">Struct Records and Discriminated Unions</span></span>

<span data-ttu-id="d2e90-152">Puede representar [registros](records.md) y [uniones discriminadas](discriminated-unions.md) como structs con el `[<Struct>]` atributo.</span><span class="sxs-lookup"><span data-stu-id="d2e90-152">You can represent [Records](records.md) and [Discriminated Unions](discriminated-unions.md) as structs with the `[<Struct>]` attribute.</span></span>  <span data-ttu-id="d2e90-153">Vea cada artículo para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d2e90-153">See each article to learn more.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2e90-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2e90-154">See also</span></span>

- [<span data-ttu-id="d2e90-155">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="d2e90-155">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="d2e90-156">Clases</span><span class="sxs-lookup"><span data-stu-id="d2e90-156">Classes</span></span>](classes.md)
- [<span data-ttu-id="d2e90-157">Registros</span><span class="sxs-lookup"><span data-stu-id="d2e90-157">Records</span></span>](records.md)
- [<span data-ttu-id="d2e90-158">Miembros</span><span class="sxs-lookup"><span data-stu-id="d2e90-158">Members</span></span>](members/index.md)
