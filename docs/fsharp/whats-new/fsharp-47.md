---
title: Novedades de F# 4,7- F# guía
description: Obtenga información general sobre las nuevas características disponibles en F# 4,7.
ms.date: 11/27/2019
ms.openlocfilehash: 203b258466cb9f1f50215ecf8884e92e7e86416b
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2019
ms.locfileid: "74644125"
---
# <a name="whats-new-in-f-47"></a><span data-ttu-id="a288d-103">Novedades de F# 4,7</span><span class="sxs-lookup"><span data-stu-id="a288d-103">What's new in F# 4.7</span></span>

<span data-ttu-id="a288d-104">F#4,7 agrega varias mejoras en el F# lenguaje.</span><span class="sxs-lookup"><span data-stu-id="a288d-104">F# 4.7 adds multiple improvements to the F# language.</span></span>

## <a name="get-started"></a><span data-ttu-id="a288d-105">Introducción</span><span class="sxs-lookup"><span data-stu-id="a288d-105">Get started</span></span>

<span data-ttu-id="a288d-106">F#4,7 está disponible en todas las distribuciones de .NET Core y las herramientas de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a288d-106">F# 4.7 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="a288d-107">Comience a usar para obtener más información. [ F# ](../get-started/index.md)</span><span class="sxs-lookup"><span data-stu-id="a288d-107">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="language-version"></a><span data-ttu-id="a288d-108">Versión de lenguaje</span><span class="sxs-lookup"><span data-stu-id="a288d-108">Language version</span></span>

<span data-ttu-id="a288d-109">El F# compilador 4,7 incorpora la capacidad de establecer la versión de lenguaje eficaz mediante una propiedad en el archivo de proyecto:</span><span class="sxs-lookup"><span data-stu-id="a288d-109">The F# 4.7 compiler introduces the ability to set your effective language version via a property in your project file:</span></span>

```xml
<PropertyGroup>
    <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="a288d-110">Puede establecerlo en los valores `4.6`, `4.7`, `latest`y `preview`.</span><span class="sxs-lookup"><span data-stu-id="a288d-110">You can set it to the values `4.6`, `4.7`, `latest`, and `preview`.</span></span> <span data-ttu-id="a288d-111">De manera predeterminada, es `latest`.</span><span class="sxs-lookup"><span data-stu-id="a288d-111">The default is `latest`.</span></span>

<span data-ttu-id="a288d-112">Si se establece en `preview`, el compilador activará F# todas las características de vista previa que se implementan en el compilador.</span><span class="sxs-lookup"><span data-stu-id="a288d-112">If you set it to `preview`, your compiler will activate all F# preview features that are implemented in your compiler.</span></span>

## <a name="implicit-yields"></a><span data-ttu-id="a288d-113">Rendimientos implícitos</span><span class="sxs-lookup"><span data-stu-id="a288d-113">Implicit yields</span></span>

<span data-ttu-id="a288d-114">Ya no es necesario aplicar la palabra clave `yield` en matrices, listas, secuencias o expresiones de cálculo, donde se puede deducir el tipo.</span><span class="sxs-lookup"><span data-stu-id="a288d-114">You no longer need to apply the `yield` keyword in arrays, lists, sequences, or computation expressions where the type can be inferred.</span></span> <span data-ttu-id="a288d-115">En el ejemplo siguiente, ambas expresiones requerían la instrucción `yield` para cada entrada F# anterior a 4,7:</span><span class="sxs-lookup"><span data-stu-id="a288d-115">In the following example, both expressions required the `yield` statement for each entry prior to F# 4.7:</span></span>

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

<span data-ttu-id="a288d-116">Si introduce una palabra clave de `yield` única, también se debe aplicar `yield` a todos los demás elementos.</span><span class="sxs-lookup"><span data-stu-id="a288d-116">If you introduce a single `yield` keyword, every other item must also have `yield` applied to it.</span></span>

<span data-ttu-id="a288d-117">Los rendimientos implícitos no se activan cuando se usan en una expresión que también usa `yield!` para hacer algo como el aplanamiento de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="a288d-117">Implicit yields are not activated when used in an expression that also uses `yield!` to do something like flatten a sequence.</span></span> <span data-ttu-id="a288d-118">En estos casos, debe seguir usando `yield`.</span><span class="sxs-lookup"><span data-stu-id="a288d-118">You must continue to use `yield` today in these cases.</span></span>

## <a name="wildcard-identifiers"></a><span data-ttu-id="a288d-119">Identificadores comodín</span><span class="sxs-lookup"><span data-stu-id="a288d-119">Wildcard identifiers</span></span>

<span data-ttu-id="a288d-120">En F# el código que implica clases, el autoidentificador debe ser siempre explícito en las declaraciones de miembros.</span><span class="sxs-lookup"><span data-stu-id="a288d-120">In F# code involving classes, the self-identifier needs to always be explicit in member declarations.</span></span> <span data-ttu-id="a288d-121">Sin embargo, en los casos en los que nunca se usa el autoidentificador, se ha utilizado tradicionalmente una Convención para usar un carácter de subrayado doble para indicar a los autoidentificadores sin nombre.</span><span class="sxs-lookup"><span data-stu-id="a288d-121">But in cases where the self-identifier is never used, it has traditionally been convention to use a double-underscore to indicate a nameless self-identifiers.</span></span> <span data-ttu-id="a288d-122">Ahora puede usar un solo carácter de subrayado:</span><span class="sxs-lookup"><span data-stu-id="a288d-122">You can now use a single underscore:</span></span>

```fsharp
type C() =
    member _.M() = ()
```

<span data-ttu-id="a288d-123">Esto también se aplica a los bucles `for`:</span><span class="sxs-lookup"><span data-stu-id="a288d-123">This also applies for `for` loops:</span></span>

```fsharp
for _ in 1..10 do printfn "Hello!"
```

## <a name="indentation-relaxations"></a><span data-ttu-id="a288d-124">Relajaciones de sangría</span><span class="sxs-lookup"><span data-stu-id="a288d-124">Indentation relaxations</span></span>

<span data-ttu-id="a288d-125">Antes de F# 4,7, los requisitos de sangría para los argumentos del constructor principal y del miembro estático requerían una sangría excesiva.</span><span class="sxs-lookup"><span data-stu-id="a288d-125">Prior to F# 4.7, the indentation requirements for primary constructor and static member arguments required excessive indentation.</span></span> <span data-ttu-id="a288d-126">Ahora solo requieren un único ámbito de sangría:</span><span class="sxs-lookup"><span data-stu-id="a288d-126">They now only require a single indentation scope:</span></span>

```fsharp
type OffsideCheck(a:int,
    b:int, c:int,
    d:int) = class end

type C() =
    static member M(a:int,
        b:int, c:int,
        d:int) = 1
```
