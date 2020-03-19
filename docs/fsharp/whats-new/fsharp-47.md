---
title: Novedades de la Guía de F 4.7 - F
description: Obtenga una visión general de las nuevas características disponibles en F 4.7.
ms.date: 11/27/2019
ms.openlocfilehash: 7a6e744a398719bcb55d168dd700459e0b122dd6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185871"
---
# <a name="whats-new-in-f-47"></a><span data-ttu-id="6535d-103">Novedades de la versión 4.7</span><span class="sxs-lookup"><span data-stu-id="6535d-103">What's new in F# 4.7</span></span>

<span data-ttu-id="6535d-104">F 4.7 agrega varias mejoras al lenguaje f.</span><span class="sxs-lookup"><span data-stu-id="6535d-104">F# 4.7 adds multiple improvements to the F# language.</span></span>

## <a name="get-started"></a><span data-ttu-id="6535d-105">Introducción</span><span class="sxs-lookup"><span data-stu-id="6535d-105">Get started</span></span>

<span data-ttu-id="6535d-106">F 4.7 está disponible en todas las distribuciones de .NET Core y las herramientas de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6535d-106">F# 4.7 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="6535d-107">[Empiece a utilizar F](../get-started/index.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="6535d-107">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="language-version"></a><span data-ttu-id="6535d-108">Versión de lenguaje</span><span class="sxs-lookup"><span data-stu-id="6535d-108">Language version</span></span>

<span data-ttu-id="6535d-109">El compilador de F 4.7 presenta la capacidad de establecer la versión de idioma efectiva a través de una propiedad en el archivo de proyecto:</span><span class="sxs-lookup"><span data-stu-id="6535d-109">The F# 4.7 compiler introduces the ability to set your effective language version via a property in your project file:</span></span>

```xml
<PropertyGroup>
    <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="6535d-110">Puede establecerlo en `4.6`los `4.7` `latest`valores `preview`, , , y .</span><span class="sxs-lookup"><span data-stu-id="6535d-110">You can set it to the values `4.6`, `4.7`, `latest`, and `preview`.</span></span> <span data-ttu-id="6535d-111">El valor predeterminado es `latest`.</span><span class="sxs-lookup"><span data-stu-id="6535d-111">The default is `latest`.</span></span>

<span data-ttu-id="6535d-112">Si lo establece `preview`en , el compilador activará todas las características de vista previa de F .</span><span class="sxs-lookup"><span data-stu-id="6535d-112">If you set it to `preview`, your compiler will activate all F# preview features that are implemented in your compiler.</span></span>

## <a name="implicit-yields"></a><span data-ttu-id="6535d-113">Rendimientos implícitos</span><span class="sxs-lookup"><span data-stu-id="6535d-113">Implicit yields</span></span>

<span data-ttu-id="6535d-114">Ya no es `yield` necesario aplicar la palabra clave en matrices, listas, secuencias o expresiones de cálculo donde se puede deducir el tipo.</span><span class="sxs-lookup"><span data-stu-id="6535d-114">You no longer need to apply the `yield` keyword in arrays, lists, sequences, or computation expressions where the type can be inferred.</span></span> <span data-ttu-id="6535d-115">En el ejemplo siguiente, `yield` ambas expresiones requerían la instrucción para cada entrada anterior a F 4.7:</span><span class="sxs-lookup"><span data-stu-id="6535d-115">In the following example, both expressions required the `yield` statement for each entry prior to F# 4.7:</span></span>

```fsharp
let s = seq { 1; 2; 3; 4; 5 }

let daysOfWeek includeWeekend =
    [
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then
            "Saturday"
            "Sunday"
    ]
```

<span data-ttu-id="6535d-116">Si introduce una `yield` sola palabra clave, `yield` todos los demás elementos también deben haberse aplicado a ella.</span><span class="sxs-lookup"><span data-stu-id="6535d-116">If you introduce a single `yield` keyword, every other item must also have `yield` applied to it.</span></span>

<span data-ttu-id="6535d-117">Los rendimientos implícitos no se activan `yield!` cuando se utilizan en una expresión que también se utiliza para hacer algo como aplanar una secuencia.</span><span class="sxs-lookup"><span data-stu-id="6535d-117">Implicit yields are not activated when used in an expression that also uses `yield!` to do something like flatten a sequence.</span></span> <span data-ttu-id="6535d-118">Debe seguir utilizando `yield` hoy en día en estos casos.</span><span class="sxs-lookup"><span data-stu-id="6535d-118">You must continue to use `yield` today in these cases.</span></span>

## <a name="wildcard-identifiers"></a><span data-ttu-id="6535d-119">Identificadores comodín</span><span class="sxs-lookup"><span data-stu-id="6535d-119">Wildcard identifiers</span></span>

<span data-ttu-id="6535d-120">En el código de F que implica clases, el autoidentificador debe ser siempre explícito en las declaraciones de miembro.</span><span class="sxs-lookup"><span data-stu-id="6535d-120">In F# code involving classes, the self-identifier needs to always be explicit in member declarations.</span></span> <span data-ttu-id="6535d-121">Pero en los casos en que el autoidentificador nunca se utiliza, tradicionalmente ha sido convención usar un carácter de subrayado doble para indicar un autoidentificador sin nombre.</span><span class="sxs-lookup"><span data-stu-id="6535d-121">But in cases where the self-identifier is never used, it has traditionally been convention to use a double-underscore to indicate a nameless self-identifiers.</span></span> <span data-ttu-id="6535d-122">Ahora puede utilizar un solo carácter de subrayado:</span><span class="sxs-lookup"><span data-stu-id="6535d-122">You can now use a single underscore:</span></span>

```fsharp
type C() =
    member _.M() = ()
```

<span data-ttu-id="6535d-123">Esto también `for` se aplica para los loopes:</span><span class="sxs-lookup"><span data-stu-id="6535d-123">This also applies for `for` loops:</span></span>

```fsharp
for _ in 1..10 do printfn "Hello!"
```

## <a name="indentation-relaxations"></a><span data-ttu-id="6535d-124">Relajaciones de sangría</span><span class="sxs-lookup"><span data-stu-id="6535d-124">Indentation relaxations</span></span>

<span data-ttu-id="6535d-125">Antes de F 4.7, los requisitos de sangría para el constructor principal y los argumentos de miembro estático requerían una sangría excesiva.</span><span class="sxs-lookup"><span data-stu-id="6535d-125">Prior to F# 4.7, the indentation requirements for primary constructor and static member arguments required excessive indentation.</span></span> <span data-ttu-id="6535d-126">Ahora solo requieren un único ámbito de sangría:</span><span class="sxs-lookup"><span data-stu-id="6535d-126">They now only require a single indentation scope:</span></span>

```fsharp
type OffsideCheck(a:int,
    b:int, c:int,
    d:int) = class end

type C() =
    static member M(a:int,
        b:int, c:int,
        d:int) = 1
```
