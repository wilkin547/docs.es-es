---
title: 'Excepciones: función failwith (F#)'
description: "Obtenga información acerca de cómo la función 'failwith' genera una excepción de F #."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: af1e3b7dc96b3b822e2e19b7bac435940d15922f
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="exceptions-the-failwith-function"></a>Excepciones: función failwith

El `failwith` función genera una excepción de F #.


## <a name="syntax"></a>Sintaxis

```fsharp
failwith error-message-string
```

## <a name="remarks"></a>Comentarios
El *cadena de mensaje de error* en la sintaxis anterior es una cadena literal o un valor de tipo `string`. Se convierte en el `Message` propiedad de la excepción.

La excepción que se genera por `failwith` es un `System.Exception` excepción, que es una referencia que tiene el nombre `Failure` en código de F #. El código siguiente muestra el uso de `failwith` para producir una excepción.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6001.fs)]
    
## <a name="see-also"></a>Vea también
[Control de excepciones](index.md)

[Tipos de excepción](exception-types.md)

[Exceptions: The `try...with` Expression](the-try-with-expression.md) (Excepciones: la expresión `try...with`)

[Exceptions: The `try...finally` Expression](the-try-finally-expression.md) (Excepciones: la expresión `try...finally`)

[Exceptions: the `raise` Function](the-raise-function.md) (Excepciones: la función `raise`)
