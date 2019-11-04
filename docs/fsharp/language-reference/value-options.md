---
title: Opciones de valores
description: Obtenga información sobre F# el tipo de opción Value, que es una versión de struct del tipo de opción.
ms.date: 02/06/2019
ms.openlocfilehash: 4dc3f7217943345b7aaf1165fd648ab2e01bd727
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424020"
---
# <a name="value-options"></a><span data-ttu-id="98886-103">Opciones de valores</span><span class="sxs-lookup"><span data-stu-id="98886-103">Value Options</span></span>

<span data-ttu-id="98886-104">El tipo de opción Value F# en se usa cuando se mantienen las dos circunstancias siguientes:</span><span class="sxs-lookup"><span data-stu-id="98886-104">The Value Option type in F# is used when the following two circumstances hold:</span></span>

1. <span data-ttu-id="98886-105">Un escenario es adecuado para una [ F# opción](options.md).</span><span class="sxs-lookup"><span data-stu-id="98886-105">A scenario is appropriate for an [F# Option](options.md).</span></span>
2. <span data-ttu-id="98886-106">El uso de una estructura proporciona una ventaja de rendimiento en su escenario.</span><span class="sxs-lookup"><span data-stu-id="98886-106">Using a struct provides a performance benefit in your scenario.</span></span>

<span data-ttu-id="98886-107">No todos los escenarios sensibles al rendimiento se "resuelven" mediante el uso de Structs.</span><span class="sxs-lookup"><span data-stu-id="98886-107">Not all performance-sensitive scenarios are "solved" by using structs.</span></span> <span data-ttu-id="98886-108">Debe tener en cuenta el costo adicional de copia cuando se usan en lugar de los tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="98886-108">You must consider the additional cost of copying when using them instead of reference types.</span></span> <span data-ttu-id="98886-109">Sin embargo, F# los programas de gran tamaño suelen crear instancias de muchos tipos opcionales que fluyen a través de rutas de acceso activas y, en tales casos, los Structs pueden obtener un mejor rendimiento general a lo largo de la duración de un programa.</span><span class="sxs-lookup"><span data-stu-id="98886-109">However, large F# programs commonly instantiate many optional types that flow through hot paths, and in such cases, structs can often yield better overall performance over the lifetime of a program.</span></span>

## <a name="definition"></a><span data-ttu-id="98886-110">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="98886-110">Definition</span></span>

<span data-ttu-id="98886-111">La opción Value se define como una [Unión discriminada de struct](discriminated-unions.md#struct-discriminated-unions) que es similar al tipo de opción de referencia.</span><span class="sxs-lookup"><span data-stu-id="98886-111">Value Option is defined as a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions) that is similar to the reference option type.</span></span> <span data-ttu-id="98886-112">Su definición se puede considerar de esta manera:</span><span class="sxs-lookup"><span data-stu-id="98886-112">Its definition can be thought of this way:</span></span>

```fsharp
[<StructuralEquality; StructuralComparison>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone
    | ValueSome of 'T
```

<span data-ttu-id="98886-113">La opción Value se ajusta a la igualdad estructural y a la comparación.</span><span class="sxs-lookup"><span data-stu-id="98886-113">Value Option conforms to structural equality and comparison.</span></span> <span data-ttu-id="98886-114">La principal diferencia es que el nombre compilado, el nombre de tipo y los nombres de caso indican que se trata de un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="98886-114">The main difference is that the compiled name, type name, and case names all indicate that it is a value type.</span></span>

## <a name="using-value-options"></a><span data-ttu-id="98886-115">Usar opciones de valor</span><span class="sxs-lookup"><span data-stu-id="98886-115">Using Value Options</span></span>

<span data-ttu-id="98886-116">Las opciones de valor se usan de la misma manera que [las opciones](options.md).</span><span class="sxs-lookup"><span data-stu-id="98886-116">Value Options are used just like [Options](options.md).</span></span> <span data-ttu-id="98886-117">`ValueSome` se utiliza para indicar que un valor está presente y `ValueNone` se utiliza cuando un valor no está presente:</span><span class="sxs-lookup"><span data-stu-id="98886-117">`ValueSome` is used to indicate that a value is present, and `ValueNone` is used when a value is not present:</span></span>

```fsharp
let tryParseDateTime (s: string) =
    match System.DateTime.TryParse(s) with
    | (true, dt) -> ValueSome dt
    | (false, _) -> ValueNone

let possibleDateString1 = "1990-12-25"
let possibleDateString2 = "This is not a date"

let result1 = tryParseDateTime possibleDateString1
let result2 = tryParseDateTime possibleDateString2

match (result1, result2) with
| ValueSome d1, ValueSome d2 -> printfn "Both are dates!"
| ValueSome d1, ValueNone -> printfn "Only the first is a date!"
| ValueNone, ValueSome d2 -> printfn "Only the second is a date!"
| ValueNone, ValueNone -> printfn "None of them are dates!"
```

<span data-ttu-id="98886-118">Como con [las opciones](options.md), la Convención de nomenclatura para una función que devuelve `ValueOption` es prefijarla con `try`.</span><span class="sxs-lookup"><span data-stu-id="98886-118">As with [Options](options.md), the naming convention for a function that returns `ValueOption` is to prefix it with `try`.</span></span>

## <a name="value-option-properties-and-methods"></a><span data-ttu-id="98886-119">Propiedades y métodos de la opción Value</span><span class="sxs-lookup"><span data-stu-id="98886-119">Value Option properties and methods</span></span>

<span data-ttu-id="98886-120">En este momento hay una propiedad para las opciones de valor: `Value`.</span><span class="sxs-lookup"><span data-stu-id="98886-120">There is one property for Value Options at this time: `Value`.</span></span> <span data-ttu-id="98886-121">Se produce una <xref:System.InvalidOperationException> si no hay ningún valor presente cuando se invoca esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="98886-121">An <xref:System.InvalidOperationException> is raised if no value is present when this property is invoked.</span></span>

## <a name="value-option-functions"></a><span data-ttu-id="98886-122">Funciones de opción de valor</span><span class="sxs-lookup"><span data-stu-id="98886-122">Value Option functions</span></span>

<span data-ttu-id="98886-123">Actualmente hay una función enlazada a módulos para las opciones de valor, `defaultValueArg`:</span><span class="sxs-lookup"><span data-stu-id="98886-123">There is currently one module-bound function for Value Options, `defaultValueArg`:</span></span>

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T
```

<span data-ttu-id="98886-124">Al igual que con la función `defaultArg`, `defaultValueArg` devuelve el valor subyacente de la opción de valor determinada si existe; de lo contrario, devuelve el valor predeterminado especificado.</span><span class="sxs-lookup"><span data-stu-id="98886-124">As with the `defaultArg` function, `defaultValueArg` returns the underlying value of the given Value Option if it exists; otherwise, it returns the specified default value.</span></span>

<span data-ttu-id="98886-125">En este momento, no hay otras funciones enlazadas a módulos para las opciones de valor.</span><span class="sxs-lookup"><span data-stu-id="98886-125">At this time, there are no other module-bound functions for Value Options.</span></span>

## <a name="see-also"></a><span data-ttu-id="98886-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="98886-126">See also</span></span>

- [<span data-ttu-id="98886-127">Opciones</span><span class="sxs-lookup"><span data-stu-id="98886-127">Options</span></span>](options.md)
