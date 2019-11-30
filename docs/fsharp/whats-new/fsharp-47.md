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
# <a name="whats-new-in-f-47"></a>Novedades de F# 4,7

F#4,7 agrega varias mejoras en el F# lenguaje.

## <a name="get-started"></a>Introducción

F#4,7 está disponible en todas las distribuciones de .NET Core y las herramientas de Visual Studio. Comience a usar para obtener más información. [ F# ](../get-started/index.md)

## <a name="language-version"></a>Versión de lenguaje

El F# compilador 4,7 incorpora la capacidad de establecer la versión de lenguaje eficaz mediante una propiedad en el archivo de proyecto:

```xml
<PropertyGroup>
    <LangVersion>preview</LangVersion>
</PropertyGroup>
```

Puede establecerlo en los valores `4.6`, `4.7`, `latest`y `preview`. De manera predeterminada, es `latest`.

Si se establece en `preview`, el compilador activará F# todas las características de vista previa que se implementan en el compilador.

## <a name="implicit-yields"></a>Rendimientos implícitos

Ya no es necesario aplicar la palabra clave `yield` en matrices, listas, secuencias o expresiones de cálculo, donde se puede deducir el tipo. En el ejemplo siguiente, ambas expresiones requerían la instrucción `yield` para cada entrada F# anterior a 4,7:

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

Si introduce una palabra clave de `yield` única, también se debe aplicar `yield` a todos los demás elementos.

Los rendimientos implícitos no se activan cuando se usan en una expresión que también usa `yield!` para hacer algo como el aplanamiento de una secuencia. En estos casos, debe seguir usando `yield`.

## <a name="wildcard-identifiers"></a>Identificadores comodín

En F# el código que implica clases, el autoidentificador debe ser siempre explícito en las declaraciones de miembros. Sin embargo, en los casos en los que nunca se usa el autoidentificador, se ha utilizado tradicionalmente una Convención para usar un carácter de subrayado doble para indicar a los autoidentificadores sin nombre. Ahora puede usar un solo carácter de subrayado:

```fsharp
type C() =
    member _.M() = ()
```

Esto también se aplica a los bucles `for`:

```fsharp
for _ in 1..10 do printfn "Hello!"
```

## <a name="indentation-relaxations"></a>Relajaciones de sangría

Antes de F# 4,7, los requisitos de sangría para los argumentos del constructor principal y del miembro estático requerían una sangría excesiva. Ahora solo requieren un único ámbito de sangría:

```fsharp
type OffsideCheck(a:int,
    b:int, c:int,
    d:int) = class end

type C() =
    static member M(a:int,
        b:int, c:int,
        d:int) = 1
```
