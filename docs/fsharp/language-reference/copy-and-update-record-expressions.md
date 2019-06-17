---
title: Expresiones de registro de copia y actualización
description: Obtenga información sobre cómo escribir una copia y actualización de expresión' ' que copia un registro existente o registro anónimo, las actualizaciones de especifica los campos y devuelve el registro actualizado o registro anónimo.
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: d16f5ca337047ab2eecc8828b21d8a423bf39a1f
ms.sourcegitcommit: c4dfe37032c64a1fba2cc3d5947550d79f95e3b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2019
ms.locfileid: "67041732"
---
# <a name="copy-and-update-record-expressions"></a>Expresiones de registro de copia y actualización

Un *copiar y actualizar la expresión de registro* es una expresión que se copia un registro existente, actualiza los campos especificados y devuelve el registro actualizado.

## <a name="syntax"></a>Sintaxis

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a>Comentarios

Registros y registros anónimos son inmutables de manera predeterminada, por lo que no es posible ninguna actualización para un registro existente. Para crear un registro actualizado de todos los campos de un registro deberá especificarse de nuevo. Para simplificar esta tarea un *copiar y actualizar la expresión* se puede usar. Esta expresión toma un registro existente, se crea uno nuevo del mismo tipo mediante el uso de los campos especificados de la expresión y el especificado por la expresión de campo que falta.

Esto puede ser útil cuando tiene que copiar un registro existente y posiblemente cambiar algunos de los valores de campo.

Tomemos como ejemplo un registro recién creado.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

Si desea actualizar solo en el campo de ese registro se podría utilizar el *copiar y actualizar la expresión de registro* similar al siguiente:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a>Vea también

- [Registros](records.md)
- [Registros anónimos](anonymous-records.md)
- [Referencia del lenguaje F#](index.md)
