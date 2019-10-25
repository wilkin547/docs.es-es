---
title: Aserciones
description: Aprenda a usar la expresión ' Assert ' como una característica de depuración para probar expresiones F# en el lenguaje de programación.
ms.date: 10/22/2019
ms.openlocfilehash: 430db20e5ca307ba43a72e678a0424e03b0ac381
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799062"
---
# <a name="assertions"></a>Aserciones

La expresión de `assert` es una característica de depuración que puede usar para probar una expresión. En caso de error en modo de depuración, una aserción genera un cuadro de diálogo de error del sistema.

## <a name="syntax"></a>Sintaxis

```fsharp
assert condition
```

## <a name="remarks"></a>Comentarios

La expresión `assert` tiene el tipo `bool -> unit`.

La función `assert` se resuelve como <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Esto significa que su comportamiento es idéntico a haber llamado a <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> directamente.

La comprobación de aserciones solo está habilitada cuando se compila en modo de depuración; es decir, si se define la constante `DEBUG`. En el sistema del proyecto, de forma predeterminada, la constante `DEBUG` se define en la configuración de depuración, pero no en la configuración de lanzamiento.

El error de aserción no se puede detectar mediante el F# control de excepciones.

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se muestra el uso de la expresión `assert`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
