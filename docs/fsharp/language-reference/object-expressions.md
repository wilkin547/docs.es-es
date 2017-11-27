---
title: Expresiones de objeto (F#)
description: "Aprenda cómo usar expresiones de objeto de F # cuando desee evitar el código adicional y la sobrecarga necesaria para crear un nuevo tipo con nombre."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c6dcf4c9-e7fd-4eee-9e4e-1176f4c27f57
ms.openlocfilehash: 28660d430473de02a8a55e37a26609827b364012
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="object-expressions"></a>Expresiones de objeto

Un *objeto expresión* es una expresión que crea una nueva instancia de un tipo de objeto anónimo creado dinámicamente que se basa en un tipo base existente, una interfaz o un conjunto de interfaces.


## <a name="syntax"></a>Sintaxis

```fsharp
// When typename is a class:
{ new typename [type-params]arguments with
    member-definitions
    [ additional-interface-definitions ]
}
// When typename is not a class:
{ new typename [generic-type-args] with
    member-definitions
    [ additional-interface-definitions ]
}
```

## <a name="remarks"></a>Comentarios
En la sintaxis anterior, el *typename* representa un tipo de clase existente o un tipo de interfaz. *parámetros de tipo* se describen los parámetros de tipo genérico opcionales. El *argumentos* se usan únicamente para los tipos de clase, que requieren parámetros de constructor. El *definiciones de miembros* son reemplazos de métodos de clase base o implementaciones de métodos abstractos de una clase base o una interfaz.

En el ejemplo siguiente se muestra distintos tipos de expresiones de objeto.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4301.fs)]

## <a name="using-object-expressions"></a>Uso de expresiones de objeto
Usar expresiones de objeto cuando desee evitar el código adicional y la sobrecarga necesaria para crear un nuevo tipo con nombre. Si se usan expresiones de objeto para minimizar el número de tipos creados en un programa, puede reducir el número de líneas de código y evitar la proliferación innecesaria de tipos. En lugar de crear muchos tipos simplemente para hacer frente a situaciones concretas, puede usar una expresión de objeto que se personaliza un tipo existente o proporcione una implementación adecuada de una interfaz para el caso concreto en cuestión.


## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](index.md)
