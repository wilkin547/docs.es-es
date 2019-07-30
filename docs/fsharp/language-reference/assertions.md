---
title: Aserciones
description: Aprenda a usar la expresión ' Assert ' como una característica de depuración para probar expresiones F# en el lenguaje de programación.
ms.date: 05/16/2016
ms.openlocfilehash: b8b7e9662143b432d650f87515d4af31cced4149
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630026"
---
# <a name="assertions"></a>Aserciones

La `assert` expresión es una característica de depuración que puede usar para probar una expresión. En caso de error en modo de depuración, una aserción genera un cuadro de diálogo de error del sistema.

## <a name="syntax"></a>Sintaxis

```fsharp
assert condition
```

## <a name="remarks"></a>Comentarios

La `assert` expresión tiene el `bool -> unit`tipo.

En la sintaxis anterior, *Condition* representa una expresión booleana que se va a probar. Si la expresión se evalúa como `true`, la ejecución continúa inalterada. Si se evalúa como `false`, se genera un cuadro de diálogo de error del sistema. El cuadro de diálogo de error tiene un título que contiene un **error de aserción**de cadena. El cuadro de diálogo contiene un seguimiento de la pila que indica dónde se produjo el error de aserción.

La comprobación de aserciones solo está habilitada cuando se compila en modo de depuración; es decir, si se define `DEBUG` la constante. En el sistema del proyecto, de forma predeterminada `DEBUG` , la constante se define en la configuración de depuración, pero no en la configuración de lanzamiento.

El error de aserción no se puede detectar mediante el F# control de excepciones.

> [!NOTE]
> La `assert` función se resuelve como <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se muestra el uso `assert` de la expresión.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
