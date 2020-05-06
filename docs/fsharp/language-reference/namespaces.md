---
title: Espacios de nombres
description: 'Obtenga información sobre cómo un espacio de nombres de F # le permite organizar el código en áreas de funcionalidad relacionada, permitiéndole adjuntar un nombre a una agrupación de elementos de programa.'
ms.date: 12/08/2018
ms.openlocfilehash: bf71843349434a1ea91c58dbc0477373dbb0c449
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82796137"
---
# <a name="namespaces"></a>Espacios de nombres

Un espacio de nombres permite organizar el código en áreas de funcionalidad relacionada, ya que permite adjuntar un nombre a una agrupación de elementos de programa de F #. Los espacios de nombres suelen ser elementos de nivel superior en archivos de F #.

## <a name="syntax"></a>Sintaxis

```fsharp
namespace [rec] [parent-namespaces.]identifier
```

## <a name="remarks"></a>Comentarios

Si desea colocar el código en un espacio de nombres, la primera declaración del archivo debe declarar el espacio de nombres. El contenido de todo el archivo se convierte entonces en parte del espacio de nombres, siempre que no exista otra declaración de espacios de nombres en el archivo. En ese caso, todo el código hasta la siguiente declaración de espacio de nombres se considera que está dentro del primer espacio de nombres.

Los espacios de nombres no pueden contener directamente valores y funciones. En su lugar, los valores y las funciones deben estar incluidos en los módulos y los módulos se incluyen en los espacios de nombres. Los espacios de nombres pueden contener tipos, módulos.

Los comentarios de documento XML se pueden declarar sobre un espacio de nombres, pero se omiten. Las directivas de compilador también se pueden declarar sobre un espacio de nombres.

Los espacios de nombres se pueden declarar explícitamente con la palabra clave namespace o implícitamente al declarar un módulo. Para declarar explícitamente un espacio de nombres, use la palabra clave namespace seguida del nombre del espacio de nombres. En el ejemplo siguiente se muestra un archivo de código que declara `Widgets` un espacio de nombres con un tipo y un módulo incluido en dicho espacio de nombres.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

Si todo el contenido del archivo está en un módulo, también puede declarar espacios de nombres implícitamente mediante la `module` palabra clave y proporcionando el nuevo nombre de espacio de nombres en el nombre completo del módulo. En el ejemplo siguiente se muestra un archivo de código que declara `Widgets` un espacio de `WidgetsModule`nombres y un módulo, que contiene una función.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

El código siguiente es equivalente al código anterior, pero el módulo es una declaración de módulo local. En ese caso, el espacio de nombres debe aparecer en su propia línea.

[!code-fsharp[Main](~/samples/snippets/fsharp/namespaces/snippet6402.fs)]

Si se necesita más de un módulo en el mismo archivo en uno o varios espacios de nombres, debe usar las declaraciones del módulo local. Al utilizar las declaraciones del módulo local, no se puede usar el espacio de nombres completo en las declaraciones del módulo. En el código siguiente se muestra un archivo que tiene una declaración de espacio de nombres y dos declaraciones de módulos locales. En este caso, los módulos se incluyen directamente en el espacio de nombres; no hay ningún módulo creado implícitamente que tenga el mismo nombre que el archivo. Cualquier otro código del archivo, como un `do` enlace, está en el espacio de nombres pero no en los módulos internos, por lo que debe calificar el miembro `widgetFunction` del módulo mediante el nombre del módulo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

La salida de este ejemplo es la siguiente.

```fsharp
Module1 10 20
Module2 5 6
```

Para obtener más información, vea [módulos](modules.md).

## <a name="nested-namespaces"></a>Espacios de nombres anidados

Al crear un espacio de nombres anidado, debe calificarlo por completo. De lo contrario, se crea un nuevo espacio de nombres de nivel superior. La sangría se omite en las declaraciones de espacio de nombres.

En el ejemplo siguiente se muestra cómo declarar un espacio de nombres anidado.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a>Espacios de nombres en archivos y ensamblados

Los espacios de nombres pueden abarcar varios archivos en un único proyecto o compilación. El término *espacio de nombres* de términos describe la parte de un espacio de nombres que se incluye en un archivo. Los espacios de nombres también pueden abarcar varios ensamblados. Por ejemplo, el `System` espacio de nombres incluye todo el .NET Framework, que abarca muchos ensamblados y contiene muchos espacios de nombres anidados.

## <a name="global-namespace"></a>Espacio de nombres global

El espacio de nombres `global` predefinido se usa para colocar nombres en el espacio de nombres de nivel superior de .net.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

También puede usar global para hacer referencia al espacio de nombres .NET de nivel superior, por ejemplo, para resolver conflictos de nombres con otros espacios de nombres.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a>Espacios de nombres recursivos

Los espacios de nombres también se pueden declarar como recursivos para permitir que todo el código contenido sea mutuamente recursivo.  Esto se hace a `namespace rec`través de. El uso `namespace rec` de puede aliviar algunos problemas al no poder escribir código referencial mutuamente entre tipos y módulos. El siguiente es un ejemplo de esto:

```fsharp
namespace rec MutualReferences

type Orientation = Up | Down
type PeelState = Peeled | Unpeeled

// This exception depends on the type below.
exception DontSqueezeTheBananaException of Banana

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

Tenga en cuenta que `DontSqueezeTheBananaException` la excepción y `Banana` la clase hacen referencia entre sí.  Además, el módulo `BananaHelpers` y la clase `Banana` también hacen referencia entre sí. No sería posible expresar en F # si se quita la `rec` palabra clave del `MutualReferences` espacio de nombres.

Esta característica también está disponible para los [módulos](modules.md)de nivel superior.

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F #](index.md)
- [Módulos](modules.md)
- [F # RFC FS-1009: permite tipos y módulos mutuamente referenciables en ámbitos mayores en archivos](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
