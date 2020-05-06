---
title: Módulos
description: 'Obtenga información sobre cómo un módulo de F # es una agrupación de código de F #, como valores, tipos y valores de función, en un programa de F #.'
ms.date: 04/24/2017
ms.openlocfilehash: 5f99bbd8069478bf0c7db2800ae545f31926728a
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82794369"
---
# <a name="modules"></a>Módulos

En el contexto del lenguaje F #, un *módulo* es una agrupación de código de f #, como valores, tipos y valores de función, en un programa de f #. Agrupar el código en módulos ayuda a mantener junto el código relacionado y a evitar conflictos de nombres en los programas.

## <a name="syntax"></a>Sintaxis

```fsharp
// Top-level module declaration.
module [accessibility-modifier] [qualified-namespace.]module-name
declarations
// Local module declaration.
module [accessibility-modifier] module-name =
    declarations
```

## <a name="remarks"></a>Comentarios

Un módulo de F # es una agrupación de construcciones de código de F #, como tipos, valores, valores de función y `do` código en enlaces. Se implementa como una clase de Common Language Runtime (CLR) que solo tiene miembros estáticos. Hay dos tipos de declaraciones de módulo, dependiendo de si el archivo completo está incluido en el módulo: una declaración de módulo de nivel superior y una declaración de módulo local. Una declaración de módulo de nivel superior incluye el archivo completo en el módulo. Una declaración de módulo de nivel superior solo puede aparecer como la primera declaración de un archivo.

En la sintaxis de la declaración de módulo de nivel superior, el *espacio* de nombres completo opcional es la secuencia de nombres de espacios de nombres anidados que contiene el módulo. El espacio de nombres completo no tiene que declararse previamente.

No es necesario aplicar sangría a las declaraciones en un módulo de nivel superior. Tiene que aplicar sangría a todas las declaraciones en los módulos locales. En una declaración de módulo local, solo las declaraciones a las que se aplica la sangría en la declaración de módulo forman parte del módulo.

Si un archivo de código no comienza con una declaración de módulo de nivel superior o una declaración de espacio de nombres, todo el contenido del archivo, incluidos los módulos locales, pasa a formar parte de un módulo de nivel superior creado implícitamente que tiene el mismo nombre que el archivo, sin la extensión, con la primera letra convertida en mayúsculas. Por ejemplo, considere el siguiente archivo.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6601.fs)]

Este archivo se compilaría como si estuviera escrito de esta manera:

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6602.fs)]

Si tiene varios módulos en un archivo, debe usar una declaración de módulo local para cada módulo. Si se declara un espacio de nombres envolvente, estos módulos forman parte del espacio de nombres envolvente. Si no se declara un espacio de nombres envolvente, los módulos forman parte del módulo de nivel superior creado implícitamente. En el ejemplo de código siguiente se muestra un archivo de código que contiene varios módulos. El compilador crea implícitamente un módulo de nivel `Multiplemodules`superior denominado `MyModule1` y `MyModule2` y se anidan en ese módulo de nivel superior.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6603.fs)]

Si tiene varios archivos en un proyecto o en una única compilación, o si está compilando una biblioteca, debe incluir una declaración de espacio de nombres o una declaración de módulo en la parte superior del archivo. El compilador de F # solo determina implícitamente un nombre de módulo cuando solo hay un archivo en un proyecto o una línea de comandos de compilación, y se crea una aplicación.

El *modificador Accessibility* puede ser uno de los siguientes: `public`, `private`,. `internal` Para obtener más información, consulta [Access Control](access-control.md). El valor predeterminado es public.

## <a name="referencing-code-in-modules"></a>Referencia al código en módulos

Al hacer referencia a funciones, tipos y valores de otro módulo, debe usar un nombre completo o abrir el módulo. Si usa un nombre completo, debe especificar los espacios de nombres, el módulo y el identificador del elemento de programa que desee. Cada parte de la ruta de acceso calificada se separa con un punto (.), como se indica a continuación.

`Namespace1.Namespace2.ModuleName.Identifier`

Puede abrir el módulo o uno o varios de los espacios de nombres para simplificar el código. Para obtener más información sobre cómo abrir espacios de nombres y módulos, vea [Import declarations: `open` The keyword](import-declarations-the-open-keyword.md).

En el ejemplo de código siguiente se muestra un módulo de nivel superior que contiene todo el código hasta el final del archivo.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6604.fs)]

Para usar este código desde otro archivo en el mismo proyecto, use nombres completos o abra el módulo antes de usar las funciones, como se muestra en los ejemplos siguientes.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6605.fs)]

## <a name="nested-modules"></a>Módulos anidados

Los módulos se pueden anidar. Se debe aplicar sangría a los módulos internos en lo que se refiere a las declaraciones de módulos externos para indicar que son módulos internos, no módulos nuevos. Por ejemplo, compare los dos ejemplos siguientes. Module `Z` es un módulo interno en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6607.fs)]

Pero el `Z` módulo es un elemento relacionado `Y` con el módulo en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6608.fs)]
El `Z` módulo también es un módulo relacionado en el código siguiente, ya que no tiene ninguna sangría en lo que se refiere a otras `Y`declaraciones del módulo.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6609.fs)]
Por último, si el módulo externo no tiene ninguna declaración y va seguido inmediatamente de otra declaración de módulo, se supone que la nueva declaración de módulo es un módulo interno, pero el compilador le advierte si la segunda definición de módulo no tiene una sangría más alejada que la primera.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6610.fs)]
Para eliminar la advertencia, aplique una sangría al módulo interno.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6611.fs)]
Si desea que todo el código de un archivo esté en un módulo externo único y desea que los módulos internos, el módulo externo no requiera el signo igual y no se tenga que aplicar sangría a las declaraciones, incluidas las declaraciones de módulo internas, que Irán en el módulo externo. Es necesario aplicar sangría a las declaraciones dentro de las declaraciones del módulo interno. En el código siguiente se muestra este caso.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6612.fs)]

## <a name="recursive-modules"></a>Módulos recursivos

F # 4,1 presenta el concepto de módulos que permiten que todo el código contenido sea recursivo.  Esto se hace a `module rec`través de.  El uso `module rec` de puede aliviar algunos problemas al no poder escribir código referencial mutuamente entre tipos y módulos.  El siguiente es un ejemplo de esto:

```fsharp
module rec RecursiveModule =
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

Tenga en cuenta que `DontSqueezeTheBananaException` la excepción y `Banana` la clase hacen referencia entre sí.  Además, el módulo `BananaHelpers` y la clase `Banana` también hacen referencia entre sí.  Esto no sería posible si se hubiera quitado la `rec` palabra clave del `RecursiveModule` módulo en F #.

Esta capacidad también es posible en los [espacios de nombres](namespaces.md) con F # 4,1.

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F #](index.md)
- [Espacios de nombres](namespaces.md)
- [F # RFC FS-1009: permite tipos y módulos mutuamente referenciables en ámbitos mayores en archivos](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
