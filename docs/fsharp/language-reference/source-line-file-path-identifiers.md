---
title: Identificadores de línea, archivo y ruta de acceso de origen
description: Obtenga información sobre cómo usar integrada F# valores de identificador que le permiten obtener acceso al origen de línea número, directorio y nombre de archivo en el código.
ms.date: 05/16/2016
ms.openlocfilehash: 3f2048aed9ef75037b43cd091a749e3d6bbaf9a3
ms.sourcegitcommit: 5e05f983e63d5bbd8c0b246d02c6e4f23d2fc1db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2019
ms.locfileid: "67152053"
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

En la tabla siguiente se resume los identificadores de línea, archivo y ruta de acceso de origen que están disponibles en F#. Estos identificadores no son macros de preprocesador; son valores integrados que son reconocidos por el compilador.

|Identificador predefinido|Descripción|
|---------------------|-----------|
|`__LINE__`|Se evalúa como el número de línea actual, teniendo en cuenta `#line` directivas.|
|`__SOURCE_DIRECTORY__`|Se evalúa como la ruta de acceso completa actual del directorio de origen, teniendo en cuenta `#line` directivas.|
|`__SOURCE_FILE__`|Se evalúa como el nombre de archivo de origen actual, sin su ruta de acceso, teniendo en cuenta `#line` directivas.|

Para obtener más información sobre la `#line` la directiva, consulte [directivas de compilador](compiler-directives.md).

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se muestra el uso de estos valores.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

Resultado:

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: Program.fs
```

## <a name="see-also"></a>Vea también

- [Directivas de compilador](compiler-directives.md)
- [Referencia del lenguaje F#](index.md)
