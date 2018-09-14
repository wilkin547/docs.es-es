---
title: Aserciones (F#)
description: "Obtenga información sobre cómo usar la expresión 'assert' como una característica de depuración para probar las expresiones en el lenguaje de programación F #."
ms.date: 05/16/2016
ms.openlocfilehash: 85b1e839bfd19bada48b7f1821d15ddd8fa77754
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "45521666"
---
# <a name="assertions"></a>Aserciones

El `assert` expresión es una característica de depuración que puede usar para probar una expresión. En caso de error en modo de depuración, una aserción genera un cuadro de diálogo de error del sistema.

## <a name="syntax"></a>Sintaxis

```fsharp
assert condition
```

## <a name="remarks"></a>Comentarios

El `assert` expresión tiene el tipo `bool -> unit`.

En la sintaxis anterior, *condición* representa una expresión booleana que se va a probar. Si la expresión se evalúa como `true`, la ejecución continúa sin ninguna variación. Si se evalúa como `false`, se genera un cuadro de diálogo de error del sistema. El cuadro de diálogo de error tiene un título que contiene la cadena **error de aserción**. El cuadro de diálogo contiene un seguimiento de pila que indica dónde se produjo el error de aserción.

Comprobación de aserción está habilitada sólo cuando se compila en modo de depuración; es decir, si la constante `DEBUG` está definido. En el sistema del proyecto, de forma predeterminada, el `DEBUG` constante se define en la configuración de depuración pero no en la configuración de lanzamiento.

No se puede detectar el error de aserción mediante el uso de control de excepciones de F #.

>[!NOTE]
El `assert` función se resuelve en <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.

## <a name="example"></a>Ejemplo

El ejemplo de código siguiente muestra el uso de la `assert` expresión.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
