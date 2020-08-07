---
title: 'Declaraciones de importación: palabra clave open'
description: 'Obtenga información sobre las declaraciones de importación de F # y cómo especifican un módulo o un espacio de nombres a cuyos elementos puede hacer referencia sin usar un nombre completo.'
ms.date: 04/04/2019
ms.openlocfilehash: 2b88427ca92212fb4a7598447dd1a5e12061093a
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855093"
---
# <a name="import-declarations-the-open-keyword"></a>Declaraciones de importación: `open` palabra clave

Una *declaración de importación* especifica un módulo o un espacio de nombres a cuyos elementos se puede hacer referencia sin usar un nombre completo.

## <a name="syntax"></a>Sintaxis

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a>Observaciones

> [!NOTE]
> La referencia de la API de docs.microsoft.com para F # no está completa. Si encuentra vínculos rotos, consulte la [documentación de la biblioteca básica de F #](https://fsharp.github.io/fsharp-core-docs/) .

La referencia al código mediante el espacio de nombres completo o la ruta de acceso del módulo cada vez puede crear código que es difícil de escribir, leer y mantener. En su lugar, puede usar la `open` palabra clave para los módulos y espacios de nombres que se usan con frecuencia, de modo que cuando se haga referencia a un miembro de ese módulo o espacio de nombres, se pueda usar la forma abreviada del nombre en lugar del nombre completo. Esta palabra clave es similar a la `using` palabra clave en C#, `using namespace` en Visual C++ y `Imports` en Visual Basic.

El módulo o espacio de nombres proporcionado debe estar en el mismo proyecto o en un proyecto o ensamblado al que se hace referencia. Si no es así, puede Agregar una referencia al proyecto o usar la `-reference` opción de línea de comandos (o su abreviatura `-r` ). Para obtener más información, consulte [Opciones del compilador](compiler-options.md).

La declaración de importación hace que los nombres estén disponibles en el código que sigue a la declaración, hasta el final del espacio de nombres, módulo o archivo envolvente.

Cuando se usan varias declaraciones de importación, deben aparecer en líneas independientes.

En el código siguiente se muestra el uso de la `open` palabra clave para simplificar el código.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

El compilador de F # no emite un error o advertencia cuando se producen ambigüedades cuando se produce el mismo nombre en más de un módulo o espacio de nombres abierto. Cuando se producen ambigüedades, F # da preferencia al módulo o espacio de nombres abierto más recientemente. Por ejemplo, en el código siguiente, `empty` significa `Seq.empty` que, aunque `empty` se encuentre en los `List` módulos y `Seq` .

```fsharp
open List
open Seq
printfn "%A" empty
```

Por lo tanto, tenga cuidado al abrir módulos o espacios de nombres como `List` o `Seq` que contengan miembros que tengan nombres idénticos; en su lugar, considere la posibilidad de usar los nombres completos. Debe evitar cualquier situación en la que el código dependa del orden de las declaraciones de importación.

## <a name="namespaces-that-are-open-by-default"></a>Espacios de nombres que están abiertos de forma predeterminada

Algunos espacios de nombres se usan con frecuencia en código de F # y se abren de forma implícita sin necesidad de una declaración de importación explícita. En la tabla siguiente se muestran los espacios de nombres que están abiertos de forma predeterminada.

|Espacio de nombres|Descripción|
|---------|-----------|
|`Microsoft.FSharp.Core`|Contiene definiciones de tipos de F # básicas para tipos integrados como `int` y `float` .|
|`Microsoft.FSharp.Core.Operators`|Contiene operaciones aritméticas básicas como `+` y `*` .|
|`Microsoft.FSharp.Collections`|Contiene clases de colección inmutables como `List` y `Array` .|
|`Microsoft.FSharp.Control`|Contiene los tipos para las construcciones de control, como la evaluación diferida y los flujos de trabajo asincrónicos.|
|`Microsoft.FSharp.Text`|Contiene funciones para la e/s con formato, como la `printf` función.|

## <a name="autoopen-attribute"></a>Atributo AutoOpen

Puede aplicar el `AutoOpen` atributo a un ensamblado si desea abrir automáticamente un espacio de nombres o módulo cuando se hace referencia al ensamblado. También puede aplicar el `AutoOpen` atributo a un módulo para abrir automáticamente ese módulo cuando se abre el espacio de nombres o el módulo primario. Para obtener más información, vea la [clase Core. autoopenattribute (](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).

## <a name="requirequalifiedaccess-attribute"></a>Atributo RequireQualifiedAccess

Algunos módulos, registros o tipos de Unión pueden especificar el `RequireQualifiedAccess` atributo. Cuando se hace referencia a elementos de dichos módulos, registros o uniones, se debe usar un nombre completo independientemente de si se incluye una declaración de importación. Si usa este atributo de forma estratégica en los tipos que definen nombres usados comúnmente, ayuda a evitar colisiones de nombres y, por tanto, hace que el código sea más resistente a los cambios en las bibliotecas. Para obtener más información, vea la [clase Core. requirequalifiedaccessattribute (](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Espacios de nombres](namespaces.md)
- [Módulos](modules.md)
