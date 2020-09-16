---
title: Tipos de excepción
description: 'Obtenga información sobre cómo definir y usar los tipos de excepción de F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 8b4ceec31a2d68abbcd025812ffeeefc0c090efb
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557234"
---
# <a name="exception-types"></a>Tipos de excepción

Hay dos categorías de excepciones en F #: tipos de excepción de .NET y tipos de excepción de F #. En este tema se describe cómo definir y usar los tipos de excepción de F #.

## <a name="syntax"></a>Sintaxis

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, *Exception-Type* es el nombre de un nuevo tipo de excepción de F # y *argument-Type* representa el tipo de un argumento que se puede proporcionar cuando se genera una excepción de este tipo. Puede especificar varios argumentos mediante un tipo de tupla para *el tipo de argumento*.

Una definición típica para una excepción de F # es similar a la siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

Puede generar una excepción de este tipo mediante la `raise` función, como se indica a continuación.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

Puede usar un tipo de excepción de F # directamente en los filtros de una `try...with` expresión, como se muestra en el ejemplo siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

El tipo de excepción que se define con la `exception` palabra clave en F # es un nuevo tipo que hereda de `System.Exception` .

## <a name="see-also"></a>Vea también

- [Control de excepciones](index.md)
- [Excepciones: la `raise` función](the-raise-function.md)
- [Jerarquía de excepciones](../../../standard/exceptions/index.md)
