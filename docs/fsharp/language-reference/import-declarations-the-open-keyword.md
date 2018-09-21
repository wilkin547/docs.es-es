---
title: 'Declaraciones de importación: la palabra clave open (F#)'
description: 'Obtenga información sobre las declaraciones de importación de F # y cómo especifican un espacio de nombres o módulo cuyos elementos puede hacer referencia sin usar un nombre completo.'
ms.date: 05/16/2016
ms.openlocfilehash: 8cae4b4f5418689bfb0933b7db4ec23a313d5ed8
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2018
ms.locfileid: "46532183"
---
# <a name="import-declarations-the-open-keyword"></a>Declaraciones de importación: La `open` palabra clave

> [!NOTE]
Los vínculos de la referencia de API de este artículo le llevarán a MSDN.  La referencia de API de docs.microsoft.com no está completa.

Un *declaración de importación* especifica un módulo o espacio de nombres cuyos elementos puede hacer referencia sin usar un nombre completo.

## <a name="syntax"></a>Sintaxis

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a>Comentarios

Hacer referencia al código mediante el uso de la ruta de acceso de espacio de nombres o módulo completo cada vez puede crear código que es difícil de escribir, leer y mantener. En su lugar, puede usar el `open` palabra clave de uso frecuente módulos y espacios de nombres para que cuando se hace referencia a un miembro de ese módulo o espacio de nombres, puede usar la forma abreviada del nombre en lugar del nombre completo. Esta palabra clave es similar a la `using` palabra clave en C#, `using namespace` en Visual C++, y `Imports` en Visual Basic.

El módulo o espacio de nombres proporcionado debe ser del mismo proyecto o en un proyecto de referencia o un ensamblado. Si no es así, puede agregar una referencia al proyecto, o usar el `-reference` comando`-`opción de línea (o su abreviatura, `-r`). Para obtener más información, consulte [Opciones del compilador](compiler-options.md).

La declaración de importación hace que los nombres que estén disponibles en el código que sigue a la declaración, hasta el final del espacio de nombres, módulo o archivo envolvente.

Cuando se usa varias declaraciones de importación, deben aparecer en líneas independientes.

El código siguiente muestra el uso de la `open` palabra clave para simplificar el código.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

El compilador de F # no emite un error o una advertencia cuando las ambigüedades se producen cuando se produce el mismo nombre en más de un espacio de nombres o módulo abierta. Cuando se producen las ambigüedades, F # da preferencia al módulo o espacio de nombres abiertos más recientemente. Por ejemplo, en el código siguiente, `empty` significa `Seq.empty`, aunque `empty` se encuentra tanto en el `List` y `Seq` módulos.

```fsharp
open List
open Seq
printfn "%A" empty
```

Por lo tanto, tenga cuidado al abrir los módulos o espacios de nombres como `List` o `Seq` que contienen miembros que tienen nombres idénticos; en su lugar, considere el uso de los nombres completos. Debe evitar cualquier situación en la que el código es dependiente en el orden de las declaraciones de importación.

## <a name="namespaces-that-are-open-by-default"></a>Espacios de nombres que están abiertos de forma predeterminada

Algunos espacios de nombres se utilizan con tanta frecuencia en que se abren implícitamente sin necesidad de una declaración de importación explícita del código de F #. La siguiente tabla muestra los espacios de nombres que se abre de forma predeterminada.

|Espacio de nombres|Descripción|
|---------|-----------|
|`Microsoft.FSharp.Core`|Contiene básicas definiciones de tipo F # para los tipos integrados como `int` y `float`.|
|`Microsoft.FSharp.Core.Operators`|Contiene operaciones aritméticas básicas, como `+` y `*`.|
|`Microsoft.FSharp.Collections`|Contiene clases de colección inmutables como `List` y `Array`.|
|`Microsoft.FSharp.Control`|Contiene tipos para las estructuras de control como evaluación diferida y los flujos de trabajo asincrónicos.|
|`Microsoft.FSharp.Text`|Contiene funciones de E/S con formato, como el `printf` función.|

## <a name="autoopen-attribute"></a>AutoOpen (atributo)

Puede aplicar el `AutoOpen` atributo a un ensamblado si desea abrir automáticamente un espacio de nombres o módulo cuando se hace referencia al ensamblado. También puede aplicar el `AutoOpen` a un módulo de ese módulo se abra automáticamente al abre el módulo primario o el espacio de nombres de atributo. Para obtener más información, consulte [Core.AutoOpenAttribute clase](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).

## <a name="requirequalifiedaccess-attribute"></a>RequireQualifiedAccess (atributo)

Algunos módulos, registros o tipos de unión pueden especificar el `RequireQualifiedAccess` atributo. Cuando se hace referencia a elementos de esos módulos, registros o uniones, debe usar un nombre completo, independientemente de si se incluye una declaración de importación. Si utiliza este atributo estratégicamente en tipos que normalmente definen los nombres utilizan, para ayudar a evitar conflictos de nombres y, por tanto, asegúrese de código sea más resistente a los cambios en las bibliotecas. Para obtener más información, consulte [Core.RequireQualifiedAccessAttribute clase](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).

## <a name="see-also"></a>Vea también

- [# Referencia del lenguaje](index.md)
- [Espacios de nombres](namespaces.md)
- [Módulos](modules.md)
