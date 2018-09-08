---
title: Módulos (F#)
description: 'Obtenga información sobre cómo un módulo de F # es una agrupación de código de F #, como valores, tipos y valores de función, en un programa de F #.'
ms.date: 04/24/2017
ms.openlocfilehash: fb0aa1d508d1141933b4fbdf10633f67ed078dc7
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44178226"
---
# <a name="modules"></a>Módulos

En el contexto del lenguaje F #, un *módulo* es una agrupación de código de F #, como valores, tipos y valores de función, en un programa de F #. Agrupar el código en módulos ayuda a mantener junto el código relacionado y a evitar conflictos de nombres en los programas.

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

Un módulo de F # es una agrupación de construcciones de código de F # como tipos, valores, valores de función y el código en `do` enlaces. Se implementa como una clase de common language runtime (CLR) que tenga solo miembros estáticos. Hay dos tipos de declaraciones de módulo, dependiendo de si el archivo completo se incluye en el módulo: una declaración de módulo de nivel superior y una declaración de módulo local. Una declaración de módulo de nivel superior incluye todo el archivo del módulo. Una declaración de módulo de nivel superior solo puede aparecer como la primera declaración en un archivo.

En la sintaxis de la declaración de módulo de nivel superior, el elemento opcional *espacio de nombres calificado* es la secuencia de nombres de espacio de nombres anidado que contiene el módulo. El espacio de nombres calificado no tienen que ser declarados previamente.

No es necesario que aplicar sangría a las declaraciones en un módulo de nivel superior. Es necesario que aplicar sangría a todas las declaraciones de módulos locales. En una declaración de módulo local, solo las declaraciones que se les aplica sangría debajo de su declaración forman parte del módulo.

Si un archivo de código no comienza con una declaración de módulo de nivel superior o una declaración de espacio de nombres, el contenido completo del archivo, incluidos los módulos locales, pasa a formar parte de un módulo de nivel superior creado implícitamente que tiene el mismo nombre que el archivo, sin la extensión, con la primera letra convertida en mayúsculas. Por ejemplo, considere el siguiente archivo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6601.fs)]

Este archivo se compilará como si estuviera escrita de esta manera:

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6602.fs)]

Si tiene varios módulos en un archivo, debe usar una declaración de módulo local para cada módulo. Si se declara un espacio de nombres envolvente, estos módulos forman parte del espacio de nombres envolvente. Si no se ha declarado un espacio de nombres envolvente, los módulos se convierten en parte del módulo de nivel superior creado implícitamente. El ejemplo de código siguiente muestra un archivo de código que contiene varios módulos. El compilador crea implícitamente un módulo de nivel superior denominado `Multiplemodules`, y `MyModule1` y `MyModule2` están anidados en ese módulo de nivel superior.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6603.fs)]

Si tiene varios archivos en un proyecto o en una única compilación, o si está creando una biblioteca, debe incluir una declaración de espacio de nombres o una declaración de módulo en la parte superior del archivo. El compilador de F # solo determina un nombre de módulo implícitamente cuando hay solo un archivo en una línea de comandos de compilación o de proyecto, y va a crear una aplicación.

El *modificador de accesibilidad* puede ser uno de los siguientes: `public`, `private`, `internal`. Para más información, vea [Access Control](access-control.md) (Control de acceso). El valor predeterminado es que sea pública.

## <a name="referencing-code-in-modules"></a>Hacer referencia al código en módulos

Cuando se hace referencia a funciones, tipos y valores de otro módulo, debe utilizar un nombre completo o abrir el módulo. Si usa un nombre completo, debe especificar los espacios de nombres, el módulo y el identificador del elemento de programa que desee. Separe cada parte de la ruta de acceso con un punto (.), como se indica a continuación.

`Namespace1.Namespace2.ModuleName.Identifier`

Puede abrir el módulo o uno o varios de los espacios de nombres para simplificar el código. Para obtener más información acerca de los espacios de nombres de apertura y los módulos, consulte [declaraciones de importación: la `open` palabra clave](import-declarations-the-open-keyword.md).

El ejemplo de código siguiente muestra un módulo de nivel superior que contiene todo el código hasta el final del archivo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6604.fs)]

Para usar este código de otro archivo en el mismo proyecto, usa nombres completos o abrir el módulo antes de utilizar las funciones, como se muestra en los ejemplos siguientes.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6605.fs)]

## <a name="nested-modules"></a>Módulos anidados

Los módulos se pueden anidar. En cuanto a las declaraciones de módulo exterior para indicar que son módulos internos, módulos nuevos no se deben aplicar sangría módulos internos. Por ejemplo, compare los dos ejemplos siguientes. Módulo `Z` es un módulo interno en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6607.fs)]

Pero el módulo `Z` es un elemento relacionado al módulo `Y` en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6608.fs)]
Módulo `Z` también es un módulo del mismo nivel en el código siguiente, porque no tiene sangría en cuanto a otras declaraciones de módulo `Y`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6609.fs)]
Por último, si el módulo exterior no tiene ninguna declaración y seguido inmediatamente de otra declaración de módulo, se supone que la nueva declaración de módulo es un módulo interno, pero el compilador le avisará si la segunda definición de módulo no se aplica sangría alejarlo de la primera.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6610.fs)]
Para eliminar la advertencia, aplicar sangría al módulo interno.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6611.fs)]
Si desea que todo el código en un archivo en un único módulo externo y desea que los módulos internos, el módulo exterior no requiere el signo igual, y no es necesario se aplica sangría a las declaraciones, incluidas las declaraciones de módulo interno, que se ubicarán en el módulo externo. Las declaraciones dentro de las declaraciones de módulo interno deben ser con sangría. El código siguiente muestra este caso.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6612.fs)]

## <a name="recursive-modules"></a>Módulos recursiva

F # 4.1 presenta la noción de módulos que permiten todo el código independiente para ser mutuamente recursivas.  Esto se realiza mediante `module rec`.  El uso de `module rec` puede aliviar algunas dificultades no se pueda escribir código mutuamente referencial entre los tipos y módulos.  Este es un ejemplo de esto:

```fsharp
module rec RecursiveModule =
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

Tenga en cuenta que la excepción `DontSqueezeTheBananaException` y la clase `Banana` ambos hacen referencia entre sí.  Además, el módulo `BananaHelpers` y la clase `Banana` también hacen referencia entre sí.  Esto no sería posible expresar en F # si ha quitado el `rec` palabra clave de la `RecursiveModule` módulo.

Esta funcionalidad también es posible en [espacios de nombres](namespaces.md) con F # 4.1.

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)  
- [Espacios de nombres](namespaces.md)  
- [F # RFC FS-1009 - permitir tipos mutuamente referenciales y módulos sobre ámbitos más amplios dentro de archivos](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)  
