---
title: Identificadores de línea, archivo y ruta de acceso de código fuente (F#)
description: 'Obtenga información sobre cómo usar F # identificador valores integrados que permiten acceder al número de línea de código fuente, directorio y el nombre de archivo en el código.'
ms.date: 05/16/2016
ms.openlocfilehash: 14f710d1412c3420ec627dc30216ba2e89f16bcd
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "43865132"
---
# <a name="source-line-file-and-path-identifiers"></a>Identificadores de línea, archivo y ruta de acceso de origen

Los identificadores `__LINE__`, `__SOURCE_DIRECTORY__` y `__SOURCE_FILE__` son valores integrados que permiten tener acceso al nombre de directorio y archivo número de línea de origen en el código.

## <a name="syntax"></a>Sintaxis

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a>Comentarios

Cada uno de estos valores tiene tipo `string`.

En la tabla siguiente se resume la línea de código fuente, archivos y los identificadores de ruta de acceso que están disponibles en F #. Estos identificadores no son macros de preprocesador; son valores integrados que son reconocidos por el compilador.

|Identificador predefinido|Descripción|
|---------------------|-----------|
|`__LINE__`|Se evalúa como el número de línea actual, teniendo en cuenta `#line` directivas.|
|`__SOURCE_DIRECTORY__`|Se evalúa como la ruta de acceso completa actual del directorio de origen, teniendo en cuenta `#line` directivas.|
|`__SOURCE_FILE__`|Se evalúa como el nombre de archivo de origen actual y su ruta de acceso, teniendo en cuenta `#line` directivas.|
Para obtener más información sobre la `#line` la directiva, consulte [directivas de compilador](compiler-directives.md).

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se muestra el uso de estos valores.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

Resultado:

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo\Program.fs
```

## <a name="see-also"></a>Vea también

- [Directivas de compilador](compiler-directives.md)
- [Referencia del lenguaje F#](index.md)
