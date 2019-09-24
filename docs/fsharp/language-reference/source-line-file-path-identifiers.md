---
title: Identificadores de línea, archivo y ruta de acceso de origen
description: Aprenda a usar valores de F# identificador integrados que le permiten tener acceso al número de línea de código fuente, el directorio y el nombre de archivo en el código.
ms.date: 05/16/2016
ms.openlocfilehash: f22c3dfb3cb106fbe45883ffd7de01feac30db00
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216746"
---
# <a name="source-line-file-and-path-identifiers"></a>Identificadores de línea, archivo y ruta de acceso de origen

Los identificadores `__LINE__` `__SOURCE_DIRECTORY__` y`__SOURCE_FILE__` son valores integrados que le permiten tener acceso al número de línea de código fuente, el directorio y el nombre de archivo en el código.

## <a name="syntax"></a>Sintaxis

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a>Comentarios

Cada uno de estos valores tiene `string`el tipo.

En la tabla siguiente se resumen los identificadores de línea, archivo y ruta de acceso de origen F#que están disponibles en. Estos identificadores no son macros de preprocesador; son valores integrados que reconoce el compilador.

|Identificador predefinido|Descripción|
|---------------------|-----------|
|`__LINE__`|Se evalúa como el número de línea actual, `#line` teniendo en cuenta las directivas.|
|`__SOURCE_DIRECTORY__`|Se evalúa como la ruta de acceso completa actual del directorio de origen `#line` , teniendo en cuenta las directivas.|
|`__SOURCE_FILE__`|Se evalúa como el nombre del archivo de código fuente actual, sin su `#line` ruta de acceso, teniendo en cuenta las directivas.|

Para obtener más información sobre `#line` la Directiva, vea [directivas de compilador](compiler-directives.md).

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se muestra el uso de estos valores.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

Resultado:

```console
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: Program.fs
```

## <a name="see-also"></a>Vea también

- [Directivas de compilador](compiler-directives.md)
- [Referencia del lenguaje F#](index.md)
