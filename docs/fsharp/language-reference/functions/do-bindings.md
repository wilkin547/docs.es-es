---
title: Enlaces do (F#)
description: "Obtenga información acerca de cómo un 'do' enlace de F # se usa para ejecutar el código sin tener que definir una función o un valor."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 4c63da0c5e2f4130d59f9efa6bc54a55e5fe9fd8
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="do-bindings"></a>do (Enlaces)

Un `do` enlace se usa para ejecutar el código sin tener que definir una función o un valor. Además, ¿se pueden ser los enlaces se usa en clases, consulte [ `do` enlaces en clases](../members/do-bindings-in-classes.md).


## <a name="syntax"></a>Sintaxis

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a>Comentarios
Use un `do` cuando desee ejecutar código independientemente de una definición de función o un valor de enlace. La expresión en una `do` enlace debe devolver `unit`. Código en un nivel superior `do` enlace se ejecuta cuando se inicializa el módulo. La palabra clave `do` es opcional.

Se pueden aplicar atributos a un nivel superior `do` enlace. Por ejemplo, si el programa utiliza la interoperabilidad COM, puede aplicar el `STAThread` de atributo para el programa. Puede hacerlo mediante el uso de un atributo en un `do` de enlace, como se muestra en el código siguiente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]
    
## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](../index.md)

[Funciones](index.md)

