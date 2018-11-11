---
title: Enlaces do (F#)
description: Obtenga información sobre cómo un 'do', enlace de F# se usa para ejecutar código sin definir una función o un valor.
ms.date: 05/16/2016
ms.openlocfilehash: 78dbf8da0fe40b5af566ad98693df1109eede7e4
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "45973149"
---
# <a name="do-bindings"></a>do (Enlaces)

Un `do` enlace se usa para ejecutar código sin definir una función o un valor. Además, ¿se pueden ser los enlaces se usa en clases, vea [ `do` Bindings in Classes](../members/do-bindings-in-classes.md).

## <a name="syntax"></a>Sintaxis

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a>Comentarios

Use un `do` enlace cuando desea ejecutar código de manera independiente de una definición de función o valor. La expresión en un `do` enlace debe devolver `unit`. El código en un nivel superior `do` enlace se ejecuta cuando se inicializa el módulo. La palabra clave `do` es opcional.

Se pueden aplicar atributos a un nivel superior `do` enlace. Por ejemplo, si el programa utiliza la interoperabilidad COM, es posible que desee aplicar el `STAThread` atributo al programa. Puede hacerlo mediante el uso de un atributo en un `do` de enlace, tal como se muestra en el código siguiente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](../index.md)
- [Funciones](index.md)
