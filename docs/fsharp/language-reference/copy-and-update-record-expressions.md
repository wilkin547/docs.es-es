---
title: Expresiones de registro de copia y actualización
description: Aprenda a escribir una "expresión de copia y actualización" que copie un registro existente o un registro anónimo, actualice los campos especificados y devuelva el registro actualizado o el registro anónimo.
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: bec3e0ac2fb34e358b199c509c4599b55d7bf35e
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739288"
---
# <a name="copy-and-update-record-expressions"></a>Expresiones de registro de copia y actualización

Una expresión de registro de *copia y actualización* es una expresión que copia un registro existente, actualiza los campos especificados y devuelve el registro actualizado.

## <a name="syntax"></a>Sintaxis

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a>Observaciones

Los registros y registros anónimos son inmutables de forma predeterminada, por lo que no es posible actualizar un registro existente. Para crear un registro actualizado, todos los campos de un registro tendrían que especificarse de nuevo. Para simplificar esta tarea se puede utilizar una expresión de *copia y actualización.* Esta expresión toma un registro existente, crea uno nuevo del mismo tipo mediante el uso de campos especificados de la expresión y el campo que falta especificado por la expresión.

Esto puede ser útil cuando tiene que copiar un registro existente y, posiblemente, cambiar algunos de los valores de campo.

Tomemos por ejemplo un registro recién creado.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

Para actualizar solo dos campos de ese registro, puede utilizar la expresión de *registro de copia y actualización:*

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a>Consulte también

- [Registros](records.md)
- [Registros anónimos](anonymous-records.md)
- [Referencia del lenguaje f](index.md)
