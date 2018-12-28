---
title: Opciones de valor
description: Obtenga información sobre la F# tipo de opción de valor, que es una versión de la estructura del tipo de opción.
ms.date: 06/16/2018
ms.openlocfilehash: d5209e620d53e12e9344faea09321f640af21491
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613432"
---
# <a name="value-options"></a><span data-ttu-id="986e6-103">Opciones de valor</span><span class="sxs-lookup"><span data-stu-id="986e6-103">Value Options</span></span>

<span data-ttu-id="986e6-104">El tipo de opción de valor F# se utiliza cuando mantiene los siguientes dos casos:</span><span class="sxs-lookup"><span data-stu-id="986e6-104">The Value Option type in F# is used when the following two circumstances hold:</span></span>

1. <span data-ttu-id="986e6-105">Un escenario es adecuado para un [ F# opción](options.md).</span><span class="sxs-lookup"><span data-stu-id="986e6-105">A scenario is appropriate for an [F# Option](options.md).</span></span>
2. <span data-ttu-id="986e6-106">Uso de un struct mejora el rendimiento en su escenario.</span><span class="sxs-lookup"><span data-stu-id="986e6-106">Using a struct provides a performance benefit in your scenario.</span></span>

<span data-ttu-id="986e6-107">No todos los escenarios sensibles al rendimiento se "solucionar" mediante el uso de estructuras.</span><span class="sxs-lookup"><span data-stu-id="986e6-107">Not all performance-sensitive scenarios are "solved" by using structs.</span></span> <span data-ttu-id="986e6-108">Debe tener en cuenta el costo adicional de copia cuando se usan en lugar de tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="986e6-108">You must consider the additional cost of copying when using them instead of reference types.</span></span> <span data-ttu-id="986e6-109">Sin embargo, gran F# programas suele crear una instancia de muchos tipos opcionales que fluyen a través de las rutas de acceso frecuente, porque las estructuras a veces pueden producir un mejor rendimiento general durante la vigencia de un programa.</span><span class="sxs-lookup"><span data-stu-id="986e6-109">However, large F# programs commonly instantiate many optional types that flow through hot paths, because structs can sometimes yield better overall performance over the lifetime of a program.</span></span>

## <a name="definition"></a><span data-ttu-id="986e6-110">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="986e6-110">Definition</span></span>

<span data-ttu-id="986e6-111">Opción de valor se define como un [unión discriminada de struct](discriminated-unions.md#struct-discriminated-unions) que es similar al tipo de opción de referencia.</span><span class="sxs-lookup"><span data-stu-id="986e6-111">Value Option is defined as a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions) that is similar to the reference option type.</span></span> <span data-ttu-id="986e6-112">De esta manera, se puede considerar su definición:</span><span class="sxs-lookup"><span data-stu-id="986e6-112">Its definition can be thought of this way:</span></span>

```fsharp
[<StructuralEquality; StructuralComparison>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone
    | ValueSome of 'T
```

<span data-ttu-id="986e6-113">Opción de valor se ajusta a la comparación e igualdad estructural.</span><span class="sxs-lookup"><span data-stu-id="986e6-113">Value Option conforms to structural equality and comparison.</span></span> <span data-ttu-id="986e6-114">La principal diferencia es que el nombre compilado, nombre de tipo y los nombres de casos indican que es un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="986e6-114">The main difference is that the compiled name, type name, and case names all indicate that it is a value type.</span></span>

## <a name="using-value-options"></a><span data-ttu-id="986e6-115">Uso de las opciones de valor</span><span class="sxs-lookup"><span data-stu-id="986e6-115">Using Value Options</span></span>

<span data-ttu-id="986e6-116">Opciones de valores se usan como [opciones](options.md).</span><span class="sxs-lookup"><span data-stu-id="986e6-116">Value Options are used just like [Options](options.md).</span></span> <span data-ttu-id="986e6-117">`ValueSome` se utiliza para indicar que un valor está presente, y `ValueNone` se usa cuando un valor no está presente:</span><span class="sxs-lookup"><span data-stu-id="986e6-117">`ValueSome` is used to indicate that a value is present, and `ValueNone` is used when a value is not present:</span></span>

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

<span data-ttu-id="986e6-118">Igual que con [opciones](options.md), la convención de nomenclatura para una función que devuelve `ValueOption` es un prefijo con `try`.</span><span class="sxs-lookup"><span data-stu-id="986e6-118">As with [Options](options.md), the naming convention for a function that returns `ValueOption` is to prefix it with `try`.</span></span>

## <a name="value-option-properties-and-methods"></a><span data-ttu-id="986e6-119">Métodos y propiedades de la opción de valor</span><span class="sxs-lookup"><span data-stu-id="986e6-119">Value Option properties and methods</span></span>

<span data-ttu-id="986e6-120">En este momento no hay una propiedad para las opciones de valor: `Value`.</span><span class="sxs-lookup"><span data-stu-id="986e6-120">There is one property for Value Options at this time: `Value`.</span></span> <span data-ttu-id="986e6-121">Un <xref:System.InvalidOperationException> se produce si ningún valor está presente cuando se invoca esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="986e6-121">An <xref:System.InvalidOperationException> is raised if no value is present when this property is invoked.</span></span>

## <a name="value-option-functions"></a><span data-ttu-id="986e6-122">Funciones con valores de opción</span><span class="sxs-lookup"><span data-stu-id="986e6-122">Value Option functions</span></span>

<span data-ttu-id="986e6-123">Actualmente hay una función de módulo enlazados para las opciones de valor, `defaultValueArg`:</span><span class="sxs-lookup"><span data-stu-id="986e6-123">There is currently one module-bound function for Value Options, `defaultValueArg`:</span></span>

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T 
```

<span data-ttu-id="986e6-124">Igual que con el `defaultArg` función, `defaultValueArg` devuelve el valor subyacente de la opción de valor determinado si existe; de lo contrario, devuelve el valor predeterminado especificado.</span><span class="sxs-lookup"><span data-stu-id="986e6-124">As with the `defaultArg` function, `defaultValueArg` returns the underlying value of the given Value Option if it exists; otherwise, it returns the specified default value.</span></span>

<span data-ttu-id="986e6-125">En este momento, no hay ningún otras funciones de módulo enlazados para las opciones de valor.</span><span class="sxs-lookup"><span data-stu-id="986e6-125">At this time, there are no other module-bound functions for Value Options.</span></span>

## <a name="see-also"></a><span data-ttu-id="986e6-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="986e6-126">See also</span></span>

- [<span data-ttu-id="986e6-127">Opciones</span><span class="sxs-lookup"><span data-stu-id="986e6-127">Options</span></span>](options.md)