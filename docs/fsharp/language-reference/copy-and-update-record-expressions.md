---
title: 'Copiar y actualizar registros expresiones (F #)'
description: "Obtenga información acerca de cómo escribir un 'copiar y actualizar registro expression' que copia las actualizaciones de registros, existente especificado campos y devuelve el registro actualizado."
keywords: "visual f#, f#, programación funcional"
author: ChrSteinert
ms.author: phcart
ms.date: 06/04/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: b5fc4ef0-64eb-4272-96a7-bb4dffbb634a
ms.openlocfilehash: 2eb51842b678780a1d6da96e237ebb92d1ea5cec
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="copy-and-update-record-expressions"></a>Expresiones de registro de copia y actualización

A *copiar y actualizar registro expresión* es una expresión que copia un registro existente, actualiza los campos especificados y devuelve el registro actualizado.


## <a name="syntax"></a>Sintaxis

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a>Comentarios
Los registros son inmutables de forma predeterminada, por lo que no es posible ninguna actualización para un registro existente. Para crear un registro actualizado todos los campos de un registro que puede especificar de nuevo. Para simplificar esta tarea un *copiar y actualizar registro expresión* se puede utilizar. Esta expresión toma un registro existente, crea una nueva del mismo tipo con campos especificados de la expresión y el especificado por la expresión de campo que no existe.
Esto puede ser útil cuando tiene que copiar un registro existente y posiblemente cambiar algunos de los valores de campo.

Tomemos como ejemplo un registro recién creado.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

Si desea actualizar solo en el campo de ese registro podría utilizar el *copiar y actualizar registro expresión* como lo siguiente:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a>Vea también
[Registros](records.md)

[Referencia del lenguaje F#](index.md)
