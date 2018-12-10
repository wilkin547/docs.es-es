---
title: Espacios de nombres (F#)
description: Obtenga información sobre cómo un F# espacio de nombres permite organizar el código en las áreas de funcionalidad relacionada por lo que le permite asociar un nombre a una agrupación de elementos de programa.
ms.date: 12/08/2018
ms.openlocfilehash: ad5cca8947d09d8480bfa418b003c84546edc29b
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169039"
---
# <a name="namespaces"></a>Espacios de nombres

Un espacio de nombres permite organizar el código en áreas de funcionalidad relacionada por lo que le permite asociar un nombre a una agrupación de F# elementos del programa. Espacios de nombres son elementos de nivel superior normalmente F# archivos.

## <a name="syntax"></a>Sintaxis

```fsharp
namespace [rec] [parent-namespaces.]identifier
```

## <a name="remarks"></a>Comentarios

Si desea colocar el código en un espacio de nombres, la primera declaración en el archivo debe declarar el espacio de nombres. El contenido del archivo completo, a continuación, pasan a formar parte del espacio de nombres, siempre no existe ninguna otra declaración de espacios de nombres más en el archivo. Si es así, se considera todo el código hasta la siguiente declaración de espacio de nombres que se encuentra en el primer espacio de nombres.

Los espacios de nombres no pueden contener directamente los valores y funciones. En su lugar, los valores y las funciones que deben incluirse en los módulos y los módulos se incluyen en los espacios de nombres. Los espacios de nombres pueden contener tipos de módulos.

Comentarios de documentación XML se pueden declarar por encima de un espacio de nombres, pero se ignoran. También se pueden declarar directivas de compilador por encima de un espacio de nombres.

Los espacios de nombres se pueden declarar explícitamente con la palabra clave de espacio de nombres, o implícitamente cuando se declara un módulo. Para declarar un espacio de nombres explícitamente, utilice la palabra clave de espacio de nombres seguida del nombre de espacio de nombres. El ejemplo siguiente muestra un archivo de código que declara un espacio de nombres `Widgets` con un tipo y un módulo incluido en ese espacio de nombres.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

Si todo el contenido del archivo está en un módulo, también puede declarar espacios de nombres de forma implícita mediante el uso de la `module` palabra clave y proporcionando el nombre de espacio de nombres nuevo en el nombre completo del módulo. El ejemplo siguiente muestra un archivo de código que declara un espacio de nombres `Widgets` y un módulo `WidgetsModule`, que contiene una función.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

El código siguiente es equivalente al código anterior, pero el módulo es una declaración de módulo local. En ese caso, el espacio de nombres debe aparecer en su propia línea.

[!code-fsharp[Main](../../../samples/snippets/fsharp/namespaces/snippet6402.fs)]

Si se requiere más de un módulo en el mismo archivo en uno o varios espacios de nombres, debe usar las declaraciones de módulo local. Cuando utiliza las declaraciones de módulo local, no puede usar el espacio de nombres completo en las declaraciones de módulo. El código siguiente muestra un archivo que tiene una declaración de espacio de nombres y dos declaraciones de módulo local. En este caso, los módulos se encuentran directamente en el espacio de nombres; No hay ningún módulo creado implícitamente que tiene el mismo nombre que el archivo. Cualquier otro código en el archivo, como un `do` enlace, está en el espacio de nombres, pero no en los módulos internos, por lo que necesita calificar los miembros de módulo `widgetFunction` utilizando el nombre del módulo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

La salida de este ejemplo es como sigue.

```fsharp
Module1 10 20
Module2 5 6
```

Para obtener más información, consulte [módulos](modules.md).

## <a name="nested-namespaces"></a>Espacios de nombres anidados

Cuando se crea un espacio de nombres anidado, debe calificar totalmente. En caso contrario, cree un nuevo espacio de nombres de nivel superior. Sangría se omite en las declaraciones de espacio de nombres.

El ejemplo siguiente muestra cómo declarar un espacio de nombres anidado.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a>Espacios de nombres de archivos y ensamblados

Los espacios de nombres pueden abarcar varios archivos en un solo proyecto o de compilación. El término *fragmento de espacio de nombres* describe la parte del espacio de nombres que se incluye en un archivo. Los espacios de nombres también pueden abarcar varios ensamblados. Por ejemplo, el `System` espacio de nombres incluye todo .NET Framework, que abarca muchos ensamblados y contiene muchos espacios de nombres anidados.

## <a name="global-namespace"></a>Namespace global

Usar el espacio de nombres predefinido `global` para colocar los nombres en el espacio de nombres de nivel superior. NET.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

También puede usar global para hacer referencia el espacio de nombres .NET nivel superior, por ejemplo, para resolver conflictos de nombres con otros espacios de nombres.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a>Espacios de nombres recursivos

También se pueden declarar espacios de nombres como recursivo para permitir todo el código independiente para ser mutuamente recursivas.  Esto se realiza mediante `namespace rec`. El uso de `namespace rec` puede aliviar algunas dificultades no se pueda escribir código mutuamente referencial entre los tipos y módulos. Este es un ejemplo de esto:

```fsharp
namespace rec MutualReferences

type Orientation = Up | Down
type PeelState = Peeled | Unpeeled

// This exception depends on the type below.
exception DontSqueezeTheBananaException of Banana

type BananaPeel() = class end

type Banana(orientation : Orientation) =
    member val IsPeeled = false with get, set
    member val Orientation = orientation with get, set
    member val Sides: PeelState list = [ Unpeeled; Unpeeled; Unpeeled; Unpeeled] with get, set

    member self.Peel() = BananaHelpers.peel self // Note the dependency on the BananaHelpers module.
    member self.SqueezeJuiceOut() = raise (DontSqueezeTheBananaException self) // This member depends on the exception above.

module BananaHelpers =
    let peel (b: Banana) =
        let flip (banana: Banana) =
            match banana.Orientation with
            | Up -> 
                banana.Orientation <- Down
                banana
            | Down -> banana

        let peelSides (banana: Banana) =
            banana.Sides
            |> List.map (function
                         | Unpeeled -> Peeled
                         | Peeled -> Peeled)

        match b.Orientation with
        | Up ->   b |> flip |> peelSides
        | Down -> b |> peelSides
```

Tenga en cuenta que la excepción `DontSqueezeTheBananaException` y la clase `Banana` ambos hacen referencia entre sí.  Además, el módulo `BananaHelpers` y la clase `Banana` también hacen referencia entre sí. Esto no sería posible expresar en F# si ha quitado el `rec` palabra clave de la `MutualReferences` espacio de nombres.

Esta característica también está disponible para su nivel superior [módulos](modules.md).

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Módulos](modules.md)
- [F#RFC FS-1009 - permitir tipos mutuamente referenciales y módulos sobre ámbitos más amplios dentro de archivos](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
