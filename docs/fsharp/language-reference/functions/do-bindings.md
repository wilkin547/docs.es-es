---
title: Enlaces do (F#)
description: "Obtenga información acerca de cómo un 'do' enlace de F # se usa para ejecutar el código sin tener que definir una función o un valor."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4c1057a3-3aa1-4b64-b46a-25ffe33f0be9
ms.openlocfilehash: f2563d384b67c005c96c2ff487c786476d385e70
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
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

