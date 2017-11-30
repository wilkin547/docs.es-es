---
title: "Identificadores de línea, archivo y ruta de acceso de código fuente (F#)"
description: "Obtenga información acerca de cómo usar F # identificador valores integrados que permiten acceder al número de línea de origen y el directorio y el nombre de archivo en el código."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4cfe7439-275c-4d08-980b-784e240bbf29
ms.openlocfilehash: 44cc0914226c120f2b877ce3decd25caa6817eec
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="source-line-file-and-path-identifiers"></a>Identificadores de línea, archivo y ruta de acceso de origen

Los identificadores de `__LINE__`, `__SOURCE_DIRECTORY__` y `__SOURCE_FILE__` son valores integrados que permiten obtener acceso al nombre de número, el directorio y el archivo de la línea de origen en el código.


## <a name="syntax"></a>Sintaxis

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a>Comentarios
Cada uno de estos valores tiene tipo `string`.

En la tabla siguiente se resume los identificadores de ruta de acceso que están disponibles en F #, de archivo y la línea de código fuente. Estos identificadores no son macros de preprocesador; son valores integrados que son reconocidos por el compilador.

|Identificador predefinido|Descripción|
|---------------------|-----------|
|`__LINE__`|Se evalúa como el número de línea actual, teniendo en cuenta `#line` directivas.|
|`__SOURCE_DIRECTORY__`|Se evalúa como la ruta de acceso completa actual del directorio de origen, teniendo en cuenta `#line` directivas.|
|`__SOURCE_FILE__`|Se evalúa como el nombre de archivo de origen actual y su ruta de acceso, teniendo en cuenta `#line` directivas.|
Para obtener más información sobre la `#line` directiva, consulte [directivas de compilador](compiler-directives.md).

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
[Directivas de compilador](compiler-directives.md)

[Referencia del lenguaje F#](index.md)
