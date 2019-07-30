---
title: Expresiones de registro de copia y actualización
description: Obtenga información sobre cómo escribir una expresión ' copiar y actualizar ' que copie un registro existente o un registro anónimo, actualice los campos especificados y devuelva el registro actualizado o el registro anónimo.
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: dfb20a6ff8282ae5988772cc0f0841db23aad942
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630379"
---
# <a name="copy-and-update-record-expressions"></a>Expresiones de registro de copia y actualización

Una *expresión de registro de copia y actualización* es una expresión que copia un registro existente, actualiza los campos especificados y devuelve el registro actualizado.

## <a name="syntax"></a>Sintaxis

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a>Comentarios

Los registros y los registros anónimos son inmutables de forma predeterminada, por lo que no se puede realizar ninguna actualización en un registro existente. Para crear un registro actualizado, deben volver a especificarse todos los campos de un registro. Para simplificar esta tarea, se puede usar una *expresión de copia y actualización* . Esta expresión toma un registro existente, crea uno nuevo del mismo tipo usando los campos especificados de la expresión y el campo que falta especificado por la expresión.

Esto puede ser útil si tiene que copiar un registro existente y, posiblemente, cambiar algunos de los valores de los campos.

Tome como ejemplo un registro recién creado.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

Si solo se actualizara en el campo de ese registro, podría usar la *expresión de registro de copia y actualización* como la siguiente:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a>Vea también

- [Registros](records.md)
- [Registros anónimos](anonymous-records.md)
- [Referencia del lenguaje F#](index.md)
