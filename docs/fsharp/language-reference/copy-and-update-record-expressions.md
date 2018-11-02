---
title: 'Copiar y actualizar las expresiones de registro (F #)'
description: Obtenga información sobre cómo escribir un "copiar y actualizar registro expression" que copia un registro, actualizaciones especifica los campos y devuelve el registro actualizado.
author: ChrSteinert
ms.date: 06/04/2016
ms.openlocfilehash: d2b089e8a7fc5c7ee26139003e23d2eaa8a3174e
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "45990848"
---
# <a name="copy-and-update-record-expressions"></a>Expresiones de registro de copia y actualización

Un *copiar y actualizar la expresión de registro* es una expresión que se copia un registro existente, actualiza los campos especificados y devuelve el registro actualizado.

## <a name="syntax"></a>Sintaxis

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a>Comentarios

Los registros son inmutables de manera predeterminada, por lo que no es posible ninguna actualización para un registro existente. Para crear un registro actualizado de todos los campos de un registro deberá especificarse de nuevo. Para simplificar esta tarea un *copiar y actualizar la expresión de registro* se puede usar. Esta expresión toma un registro existente, se crea uno nuevo del mismo tipo mediante el uso de los campos especificados de la expresión y el especificado por la expresión de campo que falta.
Esto puede ser útil cuando tiene que copiar un registro existente y posiblemente cambiar algunos de los valores de campo.

Tomemos como ejemplo un registro recién creado.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

Si desea actualizar solo en el campo de ese registro se podría utilizar el *copiar y actualizar la expresión de registro* similar al siguiente:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a>Vea también

- [Registros](records.md)
- [Referencia del lenguaje F#](index.md)
