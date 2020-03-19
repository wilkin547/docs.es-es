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
# <a name="whats-new-in-f-47"></a>Novedades de la versión 4.7

F 4.7 agrega varias mejoras al lenguaje f.

## <a name="get-started"></a>Introducción

F 4.7 está disponible en todas las distribuciones de .NET Core y las herramientas de Visual Studio. [Empiece a utilizar F](../get-started/index.md) para obtener más información.

## <a name="language-version"></a>Versión de lenguaje

El compilador de F 4.7 presenta la capacidad de establecer la versión de idioma efectiva a través de una propiedad en el archivo de proyecto:

```xml
<PropertyGroup>
    <LangVersion>preview</LangVersion>
</PropertyGroup>
```

Puede establecerlo en `4.6`los `4.7` `latest`valores `preview`, , , y . El valor predeterminado es `latest`.

Si lo establece `preview`en , el compilador activará todas las características de vista previa de F .

## <a name="implicit-yields"></a>Rendimientos implícitos

Ya no es `yield` necesario aplicar la palabra clave en matrices, listas, secuencias o expresiones de cálculo donde se puede deducir el tipo. En el ejemplo siguiente, `yield` ambas expresiones requerían la instrucción para cada entrada anterior a F 4.7:

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

Si introduce una `yield` sola palabra clave, `yield` todos los demás elementos también deben haberse aplicado a ella.

Los rendimientos implícitos no se activan `yield!` cuando se utilizan en una expresión que también se utiliza para hacer algo como aplanar una secuencia. Debe seguir utilizando `yield` hoy en día en estos casos.

## <a name="wildcard-identifiers"></a>Identificadores comodín

En el código de F que implica clases, el autoidentificador debe ser siempre explícito en las declaraciones de miembro. Pero en los casos en que el autoidentificador nunca se utiliza, tradicionalmente ha sido convención usar un carácter de subrayado doble para indicar un autoidentificador sin nombre. Ahora puede utilizar un solo carácter de subrayado:

```fsharp
type C() =
    member _.M() = ()
```

Esto también `for` se aplica para los loopes:

```fsharp
for _ in 1..10 do printfn "Hello!"
```

## <a name="indentation-relaxations"></a>Relajaciones de sangría

Antes de F 4.7, los requisitos de sangría para el constructor principal y los argumentos de miembro estático requerían una sangría excesiva. Ahora solo requieren un único ámbito de sangría:

```fsharp
type OffsideCheck(a:int,
    b:int, c:int,
    d:int) = class end

type C() =
    static member M(a:int,
        b:int, c:int,
        d:int) = 1
```
