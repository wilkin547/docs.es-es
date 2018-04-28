---
title: Aserciones (F#)
description: "Obtenga información acerca de cómo usar la expresión 'assert' como una característica de depuración para probar expresiones en el lenguaje de programación de F #."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 195b4a34977a63d92559003b5cd0bb89490a1e7a
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="assertions"></a>Aserciones

El `assert` expresión es una característica de depuración que puede usar para probar una expresión. En caso de error en modo de depuración, una aserción genera un cuadro de diálogo de error del sistema.

## <a name="syntax"></a>Sintaxis

```fsharp
assert condition
```

## <a name="remarks"></a>Comentarios

El `assert` expresión tiene el tipo `bool -> unit`.

En la sintaxis anterior, *condición* representa una expresión booleana que se va a probar. Si la expresión se evalúa como `true`, la ejecución continúa sin ninguna variación. Si se evalúa como `false`, se genera un cuadro de diálogo de error de sistema. El cuadro de diálogo de error tiene un título que contiene la cadena **error de aserción**. El cuadro de diálogo contiene un seguimiento de pila que indica dónde se produjo el error de aserción.

Comprobación de aserción está habilitada sólo cuando se compila en modo de depuración; es decir, si la constante `DEBUG` se define. En el sistema del proyecto, de forma predeterminada, la `DEBUG` constante se define en la configuración de depuración pero no en la configuración de lanzamiento.

No se puede detectar el error de aserción, use el control de excepción de F #.

>[!NOTE]
El `assert` función se resuelve como <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se muestra el uso de la `assert` expresión.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]
    
## <a name="see-also"></a>Vea también

[Referencia del lenguaje F#](index.md)
