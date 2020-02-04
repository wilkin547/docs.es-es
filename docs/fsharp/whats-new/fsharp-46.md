---
title: Novedades de F# 4,6- F# guía
description: Obtenga información general sobre las nuevas características disponibles en F# 4,6.
ms.date: 11/27/2019
ms.openlocfilehash: 620c1edd8ea212fee306a02d5844b6b322808251
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980397"
---
# <a name="whats-new-in-f-46"></a>Novedades de F# 4,6

F#4,6 agrega varias mejoras en el F# lenguaje.

## <a name="get-started"></a>Primeros pasos

F#4,6 está disponible en todas las distribuciones de .NET Core y las herramientas de Visual Studio. Comience a usar para obtener más información. [ F# ](../get-started/index.md)

## <a name="anonymous-records"></a>Registros anónimos

[Los registros anónimos](../language-reference/anonymous-records.md) son un nuevo F# tipo de tipo F# introducido en 4,6. Son agregados simples de valores con nombre que no es necesario declarar antes de su uso. Puede declararlos como Structs o tipos de referencia. Son tipos de referencia de forma predeterminada.

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    {| Diameter = d; Area = a; Circumference = c |}

let r = 2.0
let stats = getCircleStats r
printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
    r stats.Diameter stats.Area stats.Circumference
```

También se pueden declarar como Structs para cuando desee agrupar tipos de valor y funcionen en escenarios con distinción de rendimiento:

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    struct {| Diameter = d; Area = a; Circumference = c |}

let r = 2.0
let stats = getCircleStats r
printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
    r stats.Diameter stats.Area stats.Circumference
```

Son bastante eficaces y se pueden usar en numerosos escenarios. Obtenga más información en [registros anónimos](../language-reference/anonymous-records.md).

## <a name="valueoption-functions"></a>Funciones de ValueOption

El tipo ValueOption agregado en F# 4,5 ahora tiene "paridad de función enlazada a módulo" con el tipo de opción. Algunos de los ejemplos más usados son los siguientes:

```fsharp
// Multiply a value option by 2 if it has  value
let xOpt = ValueSome 99
let result = xOpt |> ValueOption.map (fun v -> v * 2)

// Reverse a string if it exists
let strOpt = ValueSome "Mirror image"
let reverse (str: string) =
    match str with
    | null
    | "" -> ValueNone
    | s ->
        str.ToCharArray()
        |> Array.rev
        |> string
        |> ValueSome

let reversedString = strOpt |> ValueOption.bind reverse
```

Esto permite usar ValueOption como opción en escenarios en los que tener un tipo de valor mejora el rendimiento.
