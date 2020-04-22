---
title: 'Declaraciones de importación: palabra clave open'
description: Obtenga información sobre las declaraciones de importación de F y cómo especifican un módulo o espacio de nombres a cuyos elementos puede hacer referencia sin usar un nombre completo.
ms.date: 04/04/2019
ms.openlocfilehash: 0baef27c7dc3181b9da0defb1c793fec04269c09
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021531"
---
# <a name="import-declarations-the-open-keyword"></a>Declaraciones de importación: la palabra clave `open`

> [!NOTE]
> Los vínculos de la referencia de API de este artículo le llevarán a MSDN.  La referencia de API de docs.microsoft.com no está completa.

Una declaración de *importación* especifica un módulo o espacio de nombres cuyos elementos se pueden hacer referencia sin usar un nombre completo.

## <a name="syntax"></a>Sintaxis

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a>Observaciones

Hacer referencia a código mediante el espacio de nombres completo o la ruta de acceso del módulo cada vez puede crear código que sea difícil de escribir, leer y mantener. En su lugar, `open` puede usar la palabra clave para módulos y espacios de nombres usados con frecuencia para que al hacer referencia a un miembro de ese módulo o espacio de nombres, pueda usar la forma abreviada del nombre en lugar del nombre completo. Esta palabra clave `using` es similar a `using namespace` la palabra clave `Imports` en C- , en Visual C+ y en Visual Basic.

El módulo o espacio de nombres proporcionado debe estar en el mismo proyecto o en un proyecto o ensamblado al que se hace referencia. Si no es así, puede agregar una referencia `-reference` al proyecto o utilizar la `-r`opción de línea de comandos (o su abreviatura). Para obtener más información, consulte [Opciones del compilador](compiler-options.md).

La declaración de importación hace que los nombres estén disponibles en el código que sigue a la declaración, hasta el final del espacio de nombres, módulo o archivo envolvente.

Cuando se utilizan varias declaraciones de importación, deben aparecer en líneas independientes.

El código siguiente muestra `open` el uso de la palabra clave para simplificar el código.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

El compilador de F no emite un error o una advertencia cuando se producen ambiguedades cuando se produce el mismo nombre en más de un módulo abierto o espacio de nombres. Cuando se producen ambiguedades, F- da preferencia al módulo o espacio de nombres abierto más recientemente. Por ejemplo, en el `empty` `Seq.empty`código siguiente, significa , aunque `empty` se encuentra en los `List` módulos y. `Seq`

```fsharp
open List
open Seq
printfn "%A" empty
```

Por lo tanto, tenga cuidado al `List` abrir `Seq` módulos o espacios de nombres como o que contienen miembros que tienen nombres idénticos; en su lugar, considere el uso de los nombres calificados. Debe evitar cualquier situación en la que el código dependa del orden de las declaraciones de importación.

## <a name="namespaces-that-are-open-by-default"></a>Espacios de nombres abiertos por defecto

Algunos espacios de nombres se usan con tanta frecuencia en el código de F que se abren implícitamente sin necesidad de una declaración de importación explícita. En la tabla siguiente se muestran los espacios de nombres que están abiertos de forma predeterminada.

|Espacio de nombres|Descripción|
|---------|-----------|
|`Microsoft.FSharp.Core`|Contiene definiciones de tipos básicas de `int` F `float`para tipos integrados, como y .|
|`Microsoft.FSharp.Core.Operators`|Contiene operaciones aritméticas básicas como `+` y `*`.|
|`Microsoft.FSharp.Collections`|Contiene clases de colección inmutables como `List` y `Array`.|
|`Microsoft.FSharp.Control`|Contiene tipos para construcciones de control como la evaluación diferida y flujos de trabajo asincrónicos.|
|`Microsoft.FSharp.Text`|Contiene funciones para E/S `printf` con formato, como la función.|

## <a name="autoopen-attribute"></a>Atributo AutoOpen

Puede aplicar `AutoOpen` el atributo a un ensamblado si desea abrir automáticamente un espacio de nombres o módulo cuando se hace referencia al ensamblado. También puede aplicar `AutoOpen` el atributo a un módulo para abrir automáticamente ese módulo cuando se abre el módulo primario o el espacio de nombres. Para obtener más información, vea [Core.AutoOpenAttribute (Clase)](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).

## <a name="requirequalifiedaccess-attribute"></a>Atributo RequireQualifiedAccess

Algunos módulos, registros o `RequireQualifiedAccess` tipos de unión pueden especificar el atributo. Al hacer referencia a elementos de esos módulos, registros o uniones, debe usar un nombre completo independientemente de si incluye una declaración de importación. Si utiliza este atributo estratégicamente en tipos que definen nombres de uso común, ayuda a evitar colisiones de nombres y, por lo tanto, hace que el código sea más resistente a los cambios en las bibliotecas. Para obtener más información, vea [Core.RequireQualifiedAccessAttribute (Clase)](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje f](index.md)
- [Espacios de nombres](namespaces.md)
- [Módulos](modules.md)
